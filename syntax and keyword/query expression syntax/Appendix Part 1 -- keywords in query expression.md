# Appendix Part 1 -- keywords in query expression
## keywords list
| keyword or phrase of keyword in LINQ | description | keyword or phrase of keyword in SQL | notice |
| :-- | :-- | :-- | :-- |
| `from {elementName} in {IQuerableObject}` | pick it as element (with name `{elementName}`) from an [`IQueryable<T>`](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable-1?view=net-9.0) object | concept is similar to `from {tableName}` | |
| `where {predicate}` | filters by predicate. Only filters the element in the predicate that is evaluated to true. | `where {predicate}` | |
| `select {columnExpression}` | select specific columns or expression about column -- `{columnExpression}` | `select {columnExpression}` | |
| `group {columnExpression} by {expressionToGroup}`| group the expression `{columnExpression}` by the expression `{expressionToGroup}` (which is relevant to the column told in `{columnExpression}`)  |  `group by {expressionToGroup}` | `{expressionToGroup}` MUST be relevant to the column told in `{columnExpression}`, it also applies to SQL. |
| `group {columnExpression} by {expressionToGroup} into {resultAliasName}`| group the expression `{columnExpression}` by the expression `{expressionToGroup}` (which is relevant to the column told in `{columnExpression}`) and alias the resultant to `{resultAliasName}` |  | You can NOT directly alias name in `group-by` clause in most standard SQL dialects. |
