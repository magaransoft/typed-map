# Typed Map [![Tests & Docs](https://github.com/magaransoft/typed-map/actions/workflows/ci.yml/badge.svg)](https://github.com/magaransoft/typed-map/actions/workflows/ci.yml)

A type-safe map for Scala 3 where each key carries its value type, eliminating runtime casts.

## Installation

Typed Map is published to Maven Central. Add the following to your `build.sbt`:

```scala
libraryDependencies += "com.magaran" %% "typed-map" % "0.1.0"
```

## Usage

```scala
import com.magaran.typedmap.*

// Define typed keys
object Name extends TypedKey[String]
object Age extends TypedKey[Int]

// Create a map
val map = TypedMap(Name -> "Alice", Age -> 30)

// Retrieve values — type-safe, no casting
val name: String = map(Name)
val age: Int = map(Age)
val maybeName: Option[String] = map.get(Name)
```

## License

MIT
