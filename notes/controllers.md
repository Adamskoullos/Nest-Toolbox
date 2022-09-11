## Controllers

---

### Basics

The blow example shows how to use the built in nest `decorators` for `routes` and `endpoints`:

```
http://localhost:3000/coffees/menu

```

```ts
import { Controller, Get } from "@nestjs/common";

@Controller("coffees")
export class CoffeesController {
  @Get("menu")
  getMenu() {
    return "Returned Coffee menu";
  }
}
```
