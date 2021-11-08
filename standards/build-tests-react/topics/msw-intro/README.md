## MSW

MSW, or Mock Service Worker, helps intercept network requests.

```js
import {rest} from 'msw'
import {setupServer} from 'msw/node'

const server = setupServer(
  rest.get('/greeting', (req, res, ctx) => {
    return res(ctx.json({greeting: 'hello there'}))
  }),
)

beforeAll(() => server.listen())

test("something", () => {
  // Override
  server.use(
    rest.get('/greeting', (req, res, ctx) => {
      return res(ctx.status(500))
    }),
  )
})
```
