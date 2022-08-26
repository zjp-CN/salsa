# 定义解析器：报告错误

解析器中的一个有趣的例子是如何处理解析错误。

因为 Salsa 函数是有记忆的，且可能不会执行，所以它们不应该有副作用，所以我们不想只调用 `eprintln!` —— 如果这样做，则只会在第一次调用函数时报告错误。

Salsa 定义了一种称为 **累加器** (accumulator) 的管理机制。

在我们的例子中，在 `ir` 模块中定义了一个名为 `Diagnotics` 的累加器结构体：

```rust
{{#include ../../../calc-example/calc/src/ir.rs:diagnostic}}
```

Accumulator structs are always newtype structs with a single field, in this case of type `Diagnostic`.
Memoized functions can *push* `Diagnostic` values onto the accumulator.
Later, you can invoke a method to find all the values that were pushed by the memoized functions
or any functions that they called
(e.g., we could get the set of `Diagnostic` values produced by the `parse_statements` function).

累加器结构体始终是具有单个字段的 newtype 结构体，在本例中为`诊断‘类型。记忆函数可以将`诊断‘值推送到累加器上。稍后，你可以调用一个方法来查找由带记忆的函数或它调用的任何函数推送的所有值(例如，我们可以获得由`parse_statements`函数生成的一组`诊断`值)。

The `Parser::report_error` method contains an example of pushing a diagnostic:

`Parser::report_error`方法包含一个推送诊断的示例：

```rust
{{#include ../../../calc-example/calc/src/parser.rs:report_error}}
```

To get the set of diagnostics produced by `parse_errors`, or any other memoized function,
we invoke the associated `accumulated` function:

要获取由`parse_errors`或任何其他记忆函数生成的诊断集，我们调用关联的`accumulated`函数：

```rust
let accumulated: Vec<Diagnostic> =
    parse_statements::accumulated::<Diagnostics>(db);
                      //            -----------
                      //     Use turbofish to specify
                      //     the diagnostics type.
```

`accumulated` takes the database `db` as argument and returns a `Vec`.

`accumulated`以数据库`db`为参数，返回`Vec`。
