# Summary

- [关于 salsa](./about_salsa.md)

# 如何使用 Salsa

- [概述](./overview.md)
- [教程： calc 语言](./tutorial.md)
  - [基本结构](./tutorial/structure.md)
  - [Jars 和数据库](./tutorial/jar.md)
  - [定义数据库结构体](./tutorial/db.md)
  - [定义 IR：各种 Salsa 结构体](./tutorial/ir.md)
  - [定义解析器：存储函数的值和输入](./tutorial/parser.md)
  - [定义解析器：报告错误](./tutorial/accumulators.md)
  - [Defining the parser: debug impls and testing](./tutorial/debug.md)
  - [Defining the checker](./tutorial/checker.md)
  - [Defining the interpreter](./tutorial/interpreter.md)
- [Reference](./reference.md)
  - [Algorithm](./reference/algorithm.md)
- [Common patterns](./common_patterns.md)
  - [Selection](./common_patterns/selection.md)
  - [On-demand (Lazy) inputs](./common_patterns/on_demand_inputs.md)
- [Tuning](./tuning.md)
- [Cycle handling](./cycles.md)
  - [Recovering via fallback](./cycles/fallback.md)

# How Salsa works internally

- [How Salsa works](./how_salsa_works.md)
- [Videos](./videos.md)
- [Plumbing](./plumbing.md)
  - [Jars and ingredients](./plumbing/jars_and_ingredients.md)
  - [Databases and runtime](./plumbing/database_and_runtime.md)
  - [Query operations](./plumbing/query_ops.md)
    - [maybe changed after](./plumbing/maybe_changed_after.md)
    - [Fetch](./plumbing/fetch.md)
    - [Derived queries flowchart](./plumbing/derived_flowchart.md)
    - [Cycle handling](./plumbing/cycles.md)
  - [Terminology](./plumbing/terminology.md)
    - [Backdate](./plumbing/terminology/backdate.md)
    - [Changed at](./plumbing/terminology/changed_at.md)
    - [Dependency](./plumbing/terminology/dependency.md)
    - [Derived query](./plumbing/terminology/derived_query.md)
    - [Durability](./plumbing/terminology/durability.md)
    - [Input query](./plumbing/terminology/input_query.md)
    - [Ingredient](./plumbing/terminology/ingredient.md)
    - [LRU](./plumbing/terminology/LRU.md)
    - [Memo](./plumbing/terminology/memo.md)
    - [Query](./plumbing/terminology/query.md)
    - [Query function](./plumbing/terminology/query_function.md)
    - [Revision](./plumbing/terminology/revision.md)
    - [Salsa item](./plumbing/terminology/salsa_item.md)
    - [Salsa struct](./plumbing/terminology/salsa_struct.md)
    - [Untracked dependency](./plumbing/terminology/untracked.md)
    - [Verified](./plumbing/terminology/verified.md)

# Appendices

- [Meta: about the book itself](./meta.md)
