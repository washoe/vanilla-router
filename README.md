# Vanilla router

I wanted to understand a bit more about ui routing, so am building one from scratch. As simple as I can get it whilst hitting the fundamentals.

- Uses `<a>` with meaningful `href`
- Fully accessible
- Correct history

# How it works

- Router links are declared as regular `<a>` elements, with a custom attribute `route`.
  - They present as regular links as far as possible.
  - The external links is there as a counter-example.
- On startup we add a click handler. This prevents the default navigation behaviour and passes the `href` our route change handler.
- The route is used to construct a hash url. If it is different to the previous one, add it to the history.
  - This prevents duplicate history entries.
- The title is updated along with the route.
- The outlet element is updated with the required html.
- `[aria-live]` ensures the change in content is announced by screen reader.

## What does it not do?

- Handle unrecognised urls, or any other route guarding.
- Focus management.
- Multi-level routing.
- Probably a whole bunch of stuff I cant think of right now.
