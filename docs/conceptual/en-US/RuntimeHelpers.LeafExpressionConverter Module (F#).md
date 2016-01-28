# RuntimeHelpers.LeafExpressionConverter Module (F#)

Contains functions that help implement F# query expressions.

**Namespace/Module Path**: Microsoft.FSharp.Linq.RuntimeHelpers

**Assembly**: FSharp.Core (in FSharp.Core.dll)


## CAPS_SYNTAX_MD

```
module LeafExpressionConverter    EvaluateQuotation : Expr -> obj    ImplicitExpressionConversionHelper : 'T -> Expression<'T>    MemberInitializationHelper : 'T -> 'T    QuotationToExpression : Expr -> Expression    QuotationToLambdaExpression : Expr<'T> -> Expression<'T>    SubstHelper : Expr * Var [] * obj [] -> Expr<'T>
```

## CAPS_REMARKS_MD

## Values


|Value|Description|
|-----|-----------|
|[EvaluateQuotation](http://msdn.microsoft.com/en-us/library/78d297ba-5713-4e81-b97c-437d816f336b): [Expr](http://msdn.microsoft.com/en-us/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65) -&gt; [obj](http://msdn.microsoft.com/en-us/library/dcf2430f-702b-40e5-a0a1-97518bf137f7)|Evaluates a subset of F# quotations by first converting to a LINQ expression, for the subset of LINQ expressions represented by the expression syntax in the C# language.|
|[ImplicitExpressionConversionHelper](http://msdn.microsoft.com/en-us/library/5f36b846-ac35-45a4-b845-5a058af226eb): 'T -&gt; **T:System.Linq.Expressions.Expression&#96;1**&lt;'T&gt;|When used in a quotation, this function indicates that a specific conversion should be performed when converting the quotation to a LINQ expression. This function should not be called directly.|
|[MemberInitializationHelper](http://msdn.microsoft.com/en-us/library/ef12e1ca-8676-43c0-b0ab-ca6e6cf120d0): 'T -&gt; 'T|When used in a quotation, this function indicates that a specific conversion should be performed when converting the quotation to a LINQ expression. This function should not be called directly.|
|[QuotationToExpression](http://msdn.microsoft.com/en-us/library/6a71ff35-492b-4047-b31e-fb2e3fc0e7ae): [Expr](http://msdn.microsoft.com/en-us/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65) -&gt; **T:System.Linq.Expressions.Expression&#96;1**|Converts a subset of F# quotations to a LINQ expression, for the subset of LINQ expressions represented by the expression syntax in the C# language.|
|[QuotationToLambdaExpression](http://msdn.microsoft.com/en-us/library/a0e524a0-1056-424f-b964-a889456e6fcb): [Expr](http://msdn.microsoft.com/en-us/library/975ca4d3-ac2b-46db-9f01-23cf8b190c6e)&lt;'T&gt; -&gt; **T:System.Linq.Expressions.Expression&#96;1**&lt;'T&gt;|Converts a subset of F# quotations to a LINQ expression, for the subset of LINQ expressions represented by the expression syntax in the C# language.|
|[SubstHelper](http://msdn.microsoft.com/en-us/library/7d59f997-d947-42cf-b57a-c51dfecc67a6): [Expr](http://msdn.microsoft.com/en-us/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65) &#42; [Var](http://msdn.microsoft.com/en-us/library/2b1237f9-d897-4bcf-872a-4a297db3f7b5) [] &#42; [obj](http://msdn.microsoft.com/en-us/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) [] -&gt; [Expr](http://msdn.microsoft.com/en-us/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)&lt;'T&gt;|A runtime helper used to evaluate nested quotation literals.|

## Platforms
Windows 8, Windows 7, Windows Server 2012, Windows Server 2008 R2


## Version Information
**F# Core Library Versions**

Supported in: 4.0, Portable




## See Also
[Microsoft.FSharp.Linq.RuntimeHelpers Namespace &#40;F&#35;&#41;](Microsoft.FSharp.Linq.RuntimeHelpers+Namespace+%28F%23%29.md)
