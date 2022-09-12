## Controllers

---

### Routes and Endpoints

The blow example shows how to use the built in nest `decorators` for `routes` and `endpoints`:

```
http://localhost:3000/coffees/all

```

```ts
import { Controller, Get } from "@nestjs/common";

@Controller("coffees")
export class CoffeesController {
  @Get("all")
  findAll() {
    return "Returns all coffees";
  }
}
```

### Params

```
http://localhost:3000/coffees/123
```

The first example grabs the params as an object allowing us to access the params via dot notation:

```ts
@Controller("coffees")
export class CoffeesController {
  @Get("all")
  findAll() {
    return "Returns all coffees";
  }

  @Get(":id")
  findOne(@Param() params) {
    return `Returns single coffee with id: ${params.id}`;
  }
}
```

> Return value: `Returns single coffee with id: 123`

The second example uses the `@params` method to pass in the specific param we want,a bit like destructuring:

```ts
@Get(':id')
  findOne(@Param('id') id: string) {
    return `Returns single coffee with id: ${id}`;
  }

```
