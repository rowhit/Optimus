## Create a Model Specification

Import the following optimization packages:
```scala
import optimus.optimization.enums._
import optimus.optimization.model._
```

Extend your object or class using ``ModelSpec``:

```scala
object Test extends ModelSpec(SolverLib.oJSolver) with App {

  val x = MPFloatVar(100, 200)
  val y = MPFloatVar(80, 170)

  maximize(-2 * x + 5 * y)
  add(y >:= -x + 200)

  start()

  release()
}
```