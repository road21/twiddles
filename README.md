# Twiddles

A twiddle list is a list of one or more values, potentially of differing types, that supports incremental creation and supports converstion to case classes that are "shape compatible".

```scala
import org.typelevel.twiddles.syntax._

case class Foo(x: Int, y: String)

val a: Option[Int] = Some(42)
// a: Option[Int] = Some(value = 42)
val b: Option[String] = Some("Hi")
// b: Option[String] = Some(value = "Hi")

val foo = (a *: b).as[Foo]
// foo: Option[Foo] = Some(value = Foo(x = 42, y = "Hi"))
```