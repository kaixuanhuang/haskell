#Type-Level Programming
* [GHC.TypeLits](https://hackage.haskell.org/package/base/docs/GHC-TypeLits.html)
* [Testing a type for (Eq a) in Haskell](http://stackoverflow.com/questions/28799005/testing-a-type-for-eq-a-in-haskell)
* [Polymorphism within higher-order functions?](http://stackoverflow.com/questions/7061538/polymorphism-within-higher-order-functions)
* [Announcing the refinement types library](http://nikita-volkov.github.io/refined/)
* [What Are Impredicative Types?](http://jozefg.bitbucket.org/posts/2014-12-23-impredicative.html)
* [A SIMPLE PROBLEM WITH RECURSIVE TYPES AND SUBTYPING](https://noamlewis.wordpress.com/2015/06/02/a-simple-problem-with-recursive-types-and-subtyping/)
* [Haskellのforallについて理解したことを書いておく(ランクN多相限定)。](http://uehaj.hatenablog.com/entry/2014/01/23/121923)
* [Existentials and the heterogenous list fallacy](http://chrisdone.com/posts/existentials)
* [Is there a function to flatten a nested list of elements?](http://stackoverflow.com/questions/5994051/is-there-a-function-to-flatten-a-nested-list-of-elements)
* [Reflecting values to types and back](https://www.fpcomplete.com/user/thoughtpolice/using-reflection)
* [TYPE COMPREHENSION](https://elvishjerricco.wordpress.com/2015/08/08/type-comprehension/)
* [k0001/exinst](https://github.com/k0001/exinst/blob/master/exinst/README.md)
* [関西関数型道場 - 第参回 S3 「型レベルプログラミング」](https://www.youtube.com/watch?v=9oamYtuzuZQ)
* [Predicates, Trees and GADTs](https://themonadreader.files.wordpress.com/2015/08/issue24.pdf)
* [24 Days of GHC Extensions: Type Operators](https://ocharles.org.uk/blog/posts/2014-12-08-type-operators.html)
* [Applying Type-Level and Generic Programming in Haskell](https://github.com/kosmikus/SSGEP)
* [Djinn, a theorem prover in Haskell, for Haskell.](http://lambda-the-ultimate.org/node/1178)
* [The type-combinators package](http://hackage.haskell.org/package/type-combinators)

```haskell
data Bottom

data (:==:) :: k -> k -> * where
   Refl :: a :==: a

type Not p = p -> Bottom

type a :/=: b = Not (a :==: b)
```

出典: [ロジックパズルの解説](http://notogawa.hatenablog.com/entry/2014/12/06/181216)

```haskell
data HList (as :: [*]) where
  HNil :: HList '[]
  HCons :: a -> HList xs -> HList (a ': xs)
```

出典: [DataKinds 言語拡張を使って Typed Heterogeneous List とその基本操作を実装してみた](http://hyone.hatenablog.com/entry/2012/12/26/181105)

##Constraint
* [The constraints package](https://hackage.haskell.org/package/constraints)
* [Constraint Kinds for GHC](http://blog.omega-prime.co.uk/?p=127)
* [The Constraint kind](https://jeltsch.wordpress.com/2013/02/14/the-constraint-kind/)
* [The constraint trick for instances](http://chrisdone.com/posts/haskell-constraint-trick)
* [mikeizbicki/ifcxt](https://github.com/mikeizbicki/ifcxt)

##Phantom Type
* [Phantom Types and Subtyping](http://www.cs.rit.edu/~mtf/research/phantom-subtyping/jfp06/jfp06.pdf)
* [型安全なリストを作るのです(｀・ω・´) ～ その1、Phantom Type（幽霊型）入門ですー＞ω＜](https://kagamilove0707.github.io/programming/2014/02/20/about-phantom-type/)
* [Phantoms](http://www.scs.stanford.edu/14sp-cs240h/slides/phantoms-slides.html)
* [What is the purpose of `Data.Proxy`?](http://stackoverflow.com/questions/22116363/what-is-the-purpose-of-data-proxy)
* [Data.Functor.Constant](https://hackage.haskell.org/package/transformers/docs/Data-Functor-Constant.html)
* [Data.Tagged](https://hackage.haskell.org/package/tagged/docs/Data-Tagged.html)

```haskell
data Circle
data Rectangle

data Shape t where
  Circle    :: Float -> Float -> Float -> Shape Circle
  Rectangle :: Float -> Float -> Float -> Float -> Shape Rectangle

surface :: Shape t -> Float
surface (Circle _ _ r) = …
surface (Rectangle x1 y1 x2 y2) = …

circum :: Shape Circle -> Float
circum (Circle _ _ r) = …
```

<https://www.reddit.com/r/haskell/comments/2jsz4t/function_on_a_single_member_of_a_sum_type/clevra9>

##Free Theorem
* [Theorems for free!](http://www.cs.sfu.ca/CourseCentral/831/burton/Notes/July14/free.pdf)
* [Parametricity](https://cubeoflambda.wordpress.com/2011/11/16/parametricity/) 
* [Parametricity Tutorial (Part 1)](http://www.well-typed.com/blog/2015/05/parametricity/)
* [Parametricity Tutorial (Part 2): Type constructors and type classes](http://www.well-typed.com/blog/2015/08/parametricity-part2/)
* [Automatic generation of free theorems](http://www-ps.iai.uni-bonn.de/cgi-bin/free-theorems-webui.cgi)
* [Are Functor instances unique?](http://stackoverflow.com/questions/19774904/are-functor-instances-unique#19775139)
  * [fmapの一意性](http://mbps.hatenablog.com/entry/2014/07/17/132835)
* [Notes on Parametricity](http://jozefg.bitbucket.org/posts/2014-12-22-parametricity.html)

##Dependent Types
* [Dependent Types](https://cubeoflambda.wordpress.com/2011/12/03/dependent-types/)
* [Fixed-Length Vector Types in Haskell, 2015](http://blog.jle.im/entry/fixed-length-vector-types-in-haskell-2015)
* [Smarter conditionals with dependent types: a quick case study](http://lambda.jstolarek.com/2015/04/smarter-conditionals-with-dependent-types-a-quick-case-study/)
* [Hasochism](http://homepages.inf.ed.ac.uk/slindley/papers/hasochism.pdf)
* [定理証明系 Haskell](http://konn-san.com/prog/2013-advent-calendar.html)
* [Approximate Dependent-Type Programming](http://okmij.org/ftp/Haskell/dependent-types.html)
* [Chris Casinghino - Making Dependent Types Practical](https://www.youtube.com/watch?v=_2jrmgO_Gq0)
* [System FC with Explicit Kind Equality](http://www.seas.upenn.edu/~sweirich/papers/fckinds.pdf)
* [Planned change to GHC: merging types and kinds](https://typesandkinds.wordpress.com/2015/08/19/planned-change-to-ghc-merging-types-and-kinds/)
* [Type is not in Type](http://jozefg.bitbucket.org/posts/2015-08-26-type-in-type.html)
* [Dependently typed programming and theorem proving in Haskell](https://jeltsch.wordpress.com/2012/04/30/dependently-typed-programming-and-theorem-proving-in-haskell/)
* [System FC with Explicit Kind Equality](http://www.cis.upenn.edu/~eir/papers/2013/fckinds/fckinds-slides.pdf)

```haskell
{-# LANGUAGE GADTs, DataKinds, KindSignatures, TypeFamilies #-}

data N = Z | S N  -- natural numbers
 
data Vec a (n :: N) where
  Nil  :: Vec a Z
  Cons :: a -> Vec a n -> Vec a (S n)

vecTail :: Vec a (S n) -> Vec a n
vecTail (Cons _ tl) = tl

data IsNull (n :: N) where
     Null    :: IsNull Z
     NotNull :: IsNull (S n)

vecNull' :: Vec a n -> IsNull n
vecNull' Nil        = Null
vecNull' (Cons _ _) = NotNull

type family Pred (n :: N) :: N where
    Pred Z     = Z
    Pred (S n) = n

shorten :: Vec a n -> Vec a (Pred n)
shorten xs = case vecNull' xs of
               Null    -> xs
               NotNull -> vecTail xs
```

出展: [Smarter conditionals with dependent types: a quick case study](http://lambda.jstolarek.com/2015/04/smarter-conditionals-with-dependent-types-a-quick-case-study/)

###一般化代数的データ型
* [一般化代数データ型(GADT)](http://www.kotha.net/ghcguide_ja/latest/data-type-extensions.html#gadt)
* [GADTs使ってみた](http://faithandbrave.hateblo.jp/entry/20111201/1322718742)
* [型安全なリストを作るのです(｀・ω・´) ～ その2、GADTsと依存型＞ω＜](https://kagamilove0707.github.io/programming/2014/02/21/gadts-and-dependent-type/)
* [GADTs - Haskell for all](http://www.haskellforall.com/2012/06/gadts.html)
* [Haskell/GADT](http://en.wikibooks.org/wiki/Haskell/GADT)
* [GADTs](http://mbps.hatenablog.com/entry/2014/10/03/010000)
* [Question: Type System and N-Dimensional Vectors](http://www.reddit.com/r/haskell/comments/2z5l9y/question_type_system_and_ndimensional_vectors/)
* [GADTs meet their match](http://research.microsoft.com/en-us/um/people/simonpj/papers/pattern-matching/gadtpm.pdf)
* [GADTs and exhaustiveness: looking for the impossible](http://www.math.nagoya-u.ac.jp/~garrigue/papers/gadtspm.pdf)
* [GADTsとかPhantom typesとかExistential typesとか](http://maoe.hatenadiary.jp/entry/20110330/1301496958)
* [DataKindsとGADTの使い方について](http://myuon-myon.hatenablog.com/entry/2015/06/14/222142)

###Multi-parameter type class
* [Multi-parameter type class](https://wiki.haskell.org/Multi-parameter_type_class)

Lucid の例

```haskell
class Term arg result | result -> arg where
  termWith :: Text -> [Attribute] -> arg -> result
-- https://hackage.haskell.org/package/lucid/docs/Lucid-Base.html#t:Term

p_ :: Term arg result => arg -> result
-- https://hackage.haskell.org/package/lucid/docs/Lucid-Html5.html#v:p_
```

* [Moving from Multiparameter Type Classes and Functional Dependencies to Type Families in Haskell](https://dikgwahlapiso.wordpress.com/2015/08/30/moving-from-multiparameter-type-classes-and-functional-dependencies-to-type-families-in-haskell/)

###Functional dependencies
* [Functional dependencies](https://www.haskell.org/haskellwiki/Functional_dependencies)
* [24 Days of GHC Extensions: Functional Dependencies](https://ocharles.org.uk/blog/posts/2014-12-14-functional-dependencies.html)
* [Typed type-level programming in Haskell, part I: functional dependencies](https://byorgey.wordpress.com/2010/06/29/typed-type-level-programming-in-haskell-part-i-functional-dependencies/)

###Type Families
* [What are type families?](https://typesandkinds.wordpress.com/2015/09/09/what-are-type-families/)
* [24 Days of GHC Extensions: Type Families](https://ocharles.org.uk/blog/posts/2014-12-12-type-families.html)
* [Fun with type functions](http://research.microsoft.com/en-us/um/people/simonpj/papers/assoc-types/fun-with-type-funs/typefun.pdf)
* [Typed type-level programming in Haskell, part II: type families](https://byorgey.wordpress.com/2010/07/06/typed-type-level-programming-in-haskell-part-ii-type-families/)
* [2 Minute intro to Associated Types / Type Families](http://nattermorphisms.blogspot.jp/2008/10/2-minute-intro-to-associated-types-type.html)
* [Type family](http://mbps.hatenablog.com/entry/2013/05/12/132507)
* [Kind](http://mbps.hatenablog.com/entry/2013/05/14/004510)
* <http://ja.stackoverflow.com/a/10475>
* [普通のtype classesとmulti-parameter type classesとfunctional dependenciesとtype families](http://maoe.hatenadiary.jp/entry/20091021/1256101883)
* [Inductive family of types](http://mbps.hatenablog.com/entry/2014/09/28/035245)
* [Injective type families](https://ghc.haskell.org/trac/ghc/wiki/InjectiveTypeFamilies)
* [Injective type families for Haskell](http://lambda.jstolarek.com/2015/05/injective-type-families-for-haskell/)
* [Type Families with Class, Type Classes with Family](http://www.diku.dk/~paba/pubs/entries/serrano15haskell.html)

```haskell
-- https://www.youtube.com/watch?v=snOBI8PcbMQ
{-# LANGUAGE TypeFamilies #-}
{-# LANGUAGE UndecidableInstances #-}

import Data.Proxy

class Eval x where
    eval :: Proxy x -> Int

data One
data Add a b

instance Eval One where
    eval _ = 1

instance (Eval a, Eval b) => Eval (Add a b) where
    eval _ = eval (Proxy :: Proxy a)
            + eval (Proxy :: Proxy b)

-----------------------------------------

data Hole

class Eval' a where
    type Value a r :: *
    eval' :: Proxy a -> (Int -> r) -> Value a r

instance Eval' One where
    type Value One r = r
    eval' _ ret = ret 1

instance (Eval' a, Eval' b) => Eval' (Add a b) where
    type Value (Add a b) r = Value a (Value b r)
    eval' _ ret = eval' (Proxy :: Proxy a) (\v1 ->
                  eval' (Proxy :: Proxy b) (\v2 ->
                  ret (v1 + v2)))

instance Eval' Hole where
    type Value Hole r = Int -> r
    eval' _ ret n = ret n
```

###Singleton
* [singletons](https://hackage.haskell.org/package/singletons)
* [Singletons](http://mbps.hatenablog.com/entry/2013/05/23/084257)