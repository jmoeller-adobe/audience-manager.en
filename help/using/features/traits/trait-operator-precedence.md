---
description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Order of Operations in Trait Builder
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
---

# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operator precedence </th> 
   <th colname="col2" class="entry"> Symbol </th> 
   <th colname="col3" class="entry"> Comments </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parenthesis </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Expressions in parenthesis are always evaluated first and follow precedence order. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Comparison operators </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Less than, greater than, less than/equal to, greater than/equal to are evaluated next. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Equality operators </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Equal to, not equal to are evaluated after the previous operators. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OR</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Working with Boolean Expressions (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Working with Comparison Operators in TraitBuilder](../../features/traits/trait-comparison-operators.md)
