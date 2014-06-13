[![Stories in Ready](https://badge.waffle.io/tkawachi/sbt-doctest.png?label=ready&title=Ready)](https://waffle.io/tkawachi/sbt-doctest)

This project is not yet published. Play with `publishLocal`.

	sbt publishLocal

In your `project/plugins.sbt`

	addSbtPlugin("com.github.tkawachi" % "sbt-doctest" % "0.1-SNAPSHOT")

and `build.sbt`

	DoctestPlugin.doctestSettings

It generates ScalaTest tests when it finds doctests in scaladoc comment.

A sample doctest.

	object Test {
	
	  /**
	   * A sample function.
	   *
	   * {{{
	   * # Python style
	   * >>> Test.f(10)
	   * 20
	   *
	   * # Scala repl style
	   * scala> Test.f(20)
	   * res1: Int = 40
	   *
	   * # Property based test
	   * prop> (i: Int) => Test.f(i) should be === (i * 2)
	   * }}}
	   */
	  def f(x: Int) = x + x
	}