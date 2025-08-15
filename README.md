# FindClosedForm
Search for a formula that yields a given number

### Documentation

#### Usage<img width="8" height="17" alt="0m0v5w4n3rqku" src="https://github.com/user-attachments/assets/3bcec326-54fc-4479-8d48-f08bb8f52861" />


<img width="119" height="19" alt="0vkuymevwfuwa" src="https://github.com/user-attachments/assets/0811fd0a-a97b-48f7-a0e3-6de7c7d1897e" />

searches for equivalents to the given number y from common mathematical functions.

<img width="134" height="19" alt="19ratzkfm7xw9" src="https://github.com/user-attachments/assets/13857bab-5509-42b5-983d-cffba7393830" />

returns up to n results for the number y.

<img width="135" height="19" alt="0meyq3i4awcxw" src="https://github.com/user-attachments/assets/60073a29-5dd5-47cc-8a66-68b5420c8ce8" />

searches for a formula with the given functional form $f$.

<img width="150" height="19" alt="06rtubm985xkh" src="https://github.com/user-attachments/assets/22afab56-8114-4e23-84ea-7c9b92b90346" />

returns up to n results.

<img width="189" height="19" alt="158jxuy0qxe26" src="https://github.com/user-attachments/assets/29be625c-4f41-47f1-8b59-e090f3c31f9d" />

searches for a formula for the given number $y$, among the given list of functional forms $f_i$.

<img width="203" height="19" alt="1n0nle9jezur8" src="https://github.com/user-attachments/assets/072580a8-8e48-40e5-b128-d17daf617ecf" />

returns up to n results.

#### Details & Options<img width="8" height="17" alt="0h3ffn7gunls6" src="https://github.com/user-attachments/assets/8c0de53a-abc2-40dd-a830-d6e21b587c70" />

$\text{FindClosedForm}$ helps to solve the fundamental problem of [Number Recognition](https://reference.wolfram.com/language/guide/NumberRecognition), by searching and finding a possible closed formula for a given number $y$, in terms of arbitrary combinations of elementary and higher mathematical functions.

Before starting any search, FindClosedForm[y,n] queries [Wolfram Alpha](https://reference.wolfram.com/language/ref/WolframAlpha) for possible closed forms of the given number. If this query does not return the required number of results with sufficient precision, the main search algorithm begins.

The fundamental strategy exploited by the search algorithm of $\text{FindClosedForm}$ is that, given a pure [Function](https://reference.wolfram.com/language/ref/Function) $f$, progressively more complex rational arguments are tried for it, until a numerical match with the given value $y$ is found. By default, this match is searched up to linear combinations with algebraic numbers (rationals or roots), as produced by [RootApproximant](https://reference.wolfram.com/language/ref/RootApproximant).

When only the first argument $y$ is specified, for each round of argument search, a further search goes on through the following quite common mathematical functions:
{[Sin](https://reference.wolfram.com/language/ref/Sin), [Cos](https://reference.wolfram.com/language/ref/Cos), [Tan](https://reference.wolfram.com/language/ref/Tan), [ArcSin](https://reference.wolfram.com/language/ref/ArcSin), [ArcCos](https://reference.wolfram.com/language/ref/ArcCos), [ArcTan](https://reference.wolfram.com/language/ref/ArcTan), [ArcCot](https://reference.wolfram.com/language/ref/ArcCot), [Log](https://reference.wolfram.com/language/ref/Log), [Exp](https://reference.wolfram.com/language/ref/Exp), [Sinh](https://reference.wolfram.com/language/ref/Sinh), [Cosh](https://reference.wolfram.com/language/ref/Cosh), [Tanh](https://reference.wolfram.com/language/ref/Tanh), [ArcSinh](https://reference.wolfram.com/language/ref/ArcSinh), [ArcCosh](https://reference.wolfram.com/language/ref/ArcCosh), [ArcTanh](https://reference.wolfram.com/language/ref/ArcTanh), [ArcCoth](https://reference.wolfram.com/language/ref/ArcCoth), [Zeta](https://reference.wolfram.com/language/ref/Zeta), [Gamma](https://reference.wolfram.com/language/ref/Gamma), [PolyGamma](https://reference.wolfram.com/language/ref/PolyGamma), [Erf](https://reference.wolfram.com/language/ref/Erf), [InverseErf](https://reference.wolfram.com/language/ref/InverseErf), [EllipticK](https://reference.wolfram.com/language/ref/EllipticK), [EllipticE](https://reference.wolfram.com/language/ref/EllipticE), [BarnesG](https://reference.wolfram.com/language/ref/BarnesG), [AiryAi](https://reference.wolfram.com/language/ref/AiryAi), [AiryBi](https://reference.wolfram.com/language/ref/AiryBi), [DedekindEta](https://reference.wolfram.com/language/ref/DedekindEta), [ModularLambda](https://reference.wolfram.com/language/ref/ModularLambda)}. In addition, FindClosedForm searches a numerical match among algebraic combinations of the following mathematical constants: {[Pi](https://reference.wolfram.com/language/ref/Pi), [GoldenRatio](https://reference.wolfram.com/language/ref/GoldenRatio), [Catalan](https://reference.wolfram.com/language/ref/Catalan), [EulerGamma](https://reference.wolfram.com/language/ref/EulerGamma), [Khinchin](https://reference.wolfram.com/language/ref/Khinchin), [Glaisher](https://reference.wolfram.com/language/ref/Glaisher)}.

The second argument can be a mathematical function $f$ or a list of them, each with arbitrary form and any number of arguments, which have to be specified as pure functions (that is, with one or more [Slot](https://reference.wolfram.com/language/ref/Slot) in their arguments).

In some cases, more than one valid formula can be found. The desired number of results must be specified as a second or third argument.

Notice that the search may take a very long time. If multiple results are requested but only partial results are found, they are [printed temporarily](https://reference.wolfram.com/language/ref/PrintTemporary) to let the user know. If the user decides to abort the search, the earlier results are kept and returned safely.

FindClosedForm accepts the following options:

<img width="751" height="363" alt="1hfnix3mqduzn" src="https://github.com/user-attachments/assets/60a1e652-7774-4da3-9a90-48533e8461b0" />

The value for the option "SignificantDigits" is set automatically to the number of digits (before 0) specified in the given number $y$ and is used to determine the order of magnitude of the relative error allowed for the numerical match. It is possible to specify a lower or higher value, so to ignore some numerical error, or require a stricter match.

The value for the option "FormulaComplexity", for any closed form formula, is a positive real which can be custom set or computed as follows: 
i) take all integers appearing in the formula, possibly being part of rational, algebraic or complex numbers; 
ii) if a root appears, duplicate its argument a number of times equal to the root degree;
iii) for each integer, compute the mean among the [square root](https://reference.wolfram.com/language/ref/Sqrt) of its absolute value, its [DigitSum](https://reference.wolfram.com/language/ref/DigitSum) and 5 times its [IntegerLength](https://reference.wolfram.com/language/ref/IntegerLength);
iv) take the total of these means.

The option "WolframAlphaQueries" sets the number of queries to be tried directly on [Wolfram Alpha](https://reference.wolfram.com/language/ref/WolframAlpha). Notice these can be unsuccessful, because the result of each query: i) may be not precise enough (as determined by "SignificantDigits"); ii) may be too complex (as determined by "FormulaComplexity"); iii) or may not have a corresponding Wolfram Language formula representation.

The option `"SearchQueries"` determines the number of results to be searched through the main search algorithm of FindClosedForm. When the default [Automatic](https://reference.wolfram.com/language/ref/Automatic) is used, it is taken to be the difference between number of results required, n, and the number of successful results returned by Wolfram|Alpha. Otherwise it is possible to set its value to 0, to make $\text{FindClosedForm}$ effectively return only the selected results from Wolfram|Alpha.

If the options `"AlgebraicAdd"` or `"AlgebraicFactor"` are set to [True](https://reference.wolfram.com/language/ref/True), the numerical match is searched up to addition or multiplication by algebraic numbers, respectively.

If the option "RootApproximantMethod" is set to "BuiltIn", these algebraic numbers are all those found through the built-in functions [RootApproximant](https://reference.wolfram.com/language/ref/RootApproximant) and [ToRadicals](https://reference.wolfram.com/language/ref/ToRadicals). If instead the option "RootApproximantMethod" is set to [Automatic](https://reference.wolfram.com/language/ref/Automatic), the algebraic numbers are assumed to have one of the absolute values equal to a "small" integer, fraction or fraction root. The [complex phase](https://reference.wolfram.com/language/ref/Arg) of  algebraic numbers is assumed to be within a π -multiple of a "small" fraction. It is also possible to specify the value for the option `"RootApproximantMethod"` as custom table of possible absolute values, or as a list of an absolute value table and complex phase table.

Summarizing, the possible values for the option "RootApproximantMethod" are the following:

<img width="654" height="105" alt="199ju3w1zggt5" src="https://github.com/user-attachments/assets/bd351420-c41e-4ad2-adb5-a2afbe52f2fc" />

If the option `"RationalSolutions"` is set to [True](https://reference.wolfram.com/language/ref/True), simple rational solutions are allowed. These are typically trivial, so unless the function searched for is the [Identity](https://reference.wolfram.com/language/ref/Identity), or both `"AlgebraicAdd"` or `"AlgebraicFactor"` are set to [False](https://reference.wolfram.com/language/ref/False), the default value for this option is [False](https://reference.wolfram.com/language/ref/False) and thus no simple rational can be returned.

If the option `"SearchArguments"` is set to [Automatic](https://reference.wolfram.com/language/ref/Automatic), the algorithm automatically tries arguments within an increasingly larger range each, with a cutoff equal to the search round (or function of it). Notice that argument ranges at successive rounds do overlap, but the program does not recompute the previously tried arguments combinations. In particular, special values for the option `"SearchRange"`, as functions of the search round, are the following:

<img width="500" height="105" alt="01hr0w2n7178r" src="https://github.com/user-attachments/assets/fccfbaa6-3c16-4899-aecc-ee0286a72354" />


Arguments to be tried can be specified through the option `"SearchArguments"` as a [List](https://reference.wolfram.com/language/ref/List) - if there is only one [Slot](https://reference.wolfram.com/language/ref/Slot) - or as a list of lists - one for each slot - or as an [Association](https://reference.wolfram.com/language/ref/Association) between slots and lists, as keys and values respectively, as follows:

<img width="570" height="105" alt="1s9ukkfon0yrd" src="https://github.com/user-attachments/assets/337fded5-c48b-47c3-96e0-9bfb1050eba2" />


The default output of $\text{FindClosedForm}$ is a [list](https://reference.wolfram.com/language/ref/List) of all the closed forms found, with no duplicates. However, sometimes the functional form may evaluate in such a way to lose information on the arguments used. Through the option `"OutputArguments"` set to [True](https://reference.wolfram.com/language/ref/True), also the arguments can be returned in the output, as keys of an [association](https://reference.wolfram.com/language/ref/Association) with the corresponding closed forms.

If the option `"SearchComplex"` is set to [True](https://reference.wolfram.com/language/ref/True), the search range, for each round, is the complex numbers extension of the ranges determined by the option "SearchRange", as realized through $\underline{\text{ResourceFunction}[\text{ComplexRange}]}.$

The value for the option `"MaxSearchRounds"` sets the number of search rounds to be tried before terminating the program. Similarly the maximum time spent by the search algorithm can be set through the option `"SearchTimeLimit"`. If the search terminates with no closed form is found, the output of `FindClosedForm` is [None](https://reference.wolfram.com/language/ref/None).

### Examples<img width="8" height="17" alt="0mn3bsv96v914" src="https://github.com/user-attachments/assets/75fc5170-f226-4284-9a90-40db3db458d5" />


#### Basic Examples

Find a possible mathematical function for a number:

```wl
FindClosedForm[0.405465]
```

<img width="52" height="30" alt="0izukabojarea" src="https://github.com/user-attachments/assets/6afa8f2a-81fe-4335-aaf5-9c002997024d" />


<!-- <img width="782" height="16" alt="1x8tyyvm9ckgn" src="https://github.com/user-attachments/assets/e0d7785a-5c78-40df-ba9b-ad2f2f1ac792" />-->


Find possible closed form for a number in terms of common mathematical functions:

```wl
FindClosedForm[3.792277]
```

<img width="94" height="30" alt="0oqors7zubg8b" src="https://github.com/user-attachments/assets/bf58e8b9-714c-4621-af3e-5470fa4d9591" />


<!--![1x8tyyvm9ckgn](img/1x8tyyvm9ckgn.png)-->

Find formulae in terms of mathematical constants:

```wl
FindClosedForm[3.311601]
```

<img width="46" height="32" alt="1snzcxq0uti3y" src="https://github.com/user-attachments/assets/d4436b56-c6b8-447f-8441-d9435e4230e0" />


```wl
FindClosedForm[1.044866]
```

<img width="74" height="34" alt="0v4ar2xgljmxi" src="https://github.com/user-attachments/assets/388f8cc4-a9f0-4dee-afba-cddf2b7f0c22" />

<!--![1x8tyyvm9ckgn](img/1x8tyyvm9ckgn.png)-->

Specify the functional form of a formula in the second argument as a pure function:

```wl
FindClosedForm[1.85653, 1/Zeta[#]^2 &]
```

<img width="68" height="39" alt="1cx9q7kdwwbdj" src="https://github.com/user-attachments/assets/c30cc16f-ed5c-431a-9ddd-cd75ce7683e5" />


```wl
FindClosedForm[-0.309033, PolyLog[#1, #2] &]
```
<img width="112" height="30" alt="0yeu9hebf3u1x" src="https://github.com/user-attachments/assets/417c2eda-16c1-41aa-8ce2-6ee8c2661a44" />

### Full documentation

See many other examples and the rest of the documentation at [this page](https://resources.wolframcloud.com/FunctionRepository/resources/FindClosedForm/) on the Wolfram Function Repository.


