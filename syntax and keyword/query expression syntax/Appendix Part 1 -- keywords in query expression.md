# Appendix Part 1 -- keywords in query expression
## keywords list
> [!IMPORTANT]
> For representing the syntax shortly and merging similar syntax into one,
>
> `keyword or phrase of keyword in LINQ` and `keyword or phrase of keyword in SQL` columns in following table
>
>  will be represented with [RE (regular expression)](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)
 
| keyword or phrase of keyword in LINQ | description | keyword or phrase of keyword in SQL | notice |
| :-- | :-- | :-- | :-- |
| from `{elementName}` in `{IQuerableObject}` | pick it as element (with name `{elementName}`) from an [`IQueryable<T>`](https://learn.microsoft.com/en-us/dotnet/api/system.linq.iqueryable-1?view=net-9.0) object | concept is similar to from `{tableName}` | |
| where `{predicate}` | filters by predicate. Only filters the element in the given predicate -- `{predicate}` that is evaluated to true. | where `{predicate}` | |
| select `{columnExpression}` | select specific columns or expression about column -- `{columnExpression}` | select `{columnExpression}` | |
| group `{columnExpression}` by `{expressionToGroup}`| group the expression `{columnExpression}` by the expression `{expressionToGroup}` (which is relevant to the column told in `{columnExpression}`)  |  group by `{expressionToGroup}` | `{expressionToGroup}` MUST be relevant to the column told in `{columnExpression}`, it also applies to SQL. |
| group `{columnExpressions} by `{expressionToGroup}` into `{resultAliasName}`| group the expression `{columnExpression}` by the expression `{expressionToGroup}` (which is relevant to the column told in `{columnExpression}`) and alias the resultant to `{resultAliasName}` |  | You can NOT directly alias name in `group-by` clause in most standard SQL dialects. |
| join `{elementNameInIQuerableObject2}` in `{IQuerableObject2}` on `{elementNameInIQuerableObject1}.{property1InIQuerableObject1}` equal `{elementNameInIQuerableObject2}.{property1InIQuerableObject2}` | do **inner join** on the relationship `{elementNameInIQuerableObject1}.{property1InIQuerableObject1}` equals to `{elementNameInIQuerableObject2}.{property1InIQuerableObject2}` | similar to inner join `{table2Name}` on `{table1Name}.{column1InTable1}` = `{table2Name}.{column1InTable2}` | |
| let `{subqueryName}` = `{expressionAboutElementNameInTable1}` | for each element in an `IQuerable<T>` object, evaluate the element with the expression `{expressionAboutElementNameInTable1}` and store it into subquery with name `{subqueryName}`. | | |
| orderby `{expressionOfElement1InQuerableObject}` (ascending|descending)? | sort the `IQuerable<T>` object by element in the `IQuerable<T>` object or expression of that in ascending order or descending order according to the specified argument is `ascending` or `descending`, or none.  | order by `{expressionOfElement1InTable}` (ASC|DESC)? | The default value is `ascending`.</br>That is, if `ascending` and `descending` are NOT specified, it will sort in ascending order. |
| orderby `{orderbyClause}`(, `{orderbyClause}`)* </br> where</br>```</br>``{orderbyClause}`:=`{expression1OfElementInQuerableBean}` (ascending|descending)? ```| 


