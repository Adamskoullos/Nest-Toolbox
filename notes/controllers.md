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

### Returning Status Codes

Nest automatically returns status codes with requests, however we can manually set these using the built-in decorator `@HttpCode`. We can pass in the enum `HttpStatus` to access any of the status codes available:

```ts
@Post()
@HttpCode(HttpStatus.GONE)
create(@Body() body) {
  return `New coffee created: ${body}`;
}

```

### Express Integration

Express is used by default and Nest provides a decorator `@Res` providing access to Expresses methods, allowing us to fully manage the response object:

```ts
@Get('all')
findAll(@Res() response) {
  response.status(200).send('Returns all coffees');
}

```
