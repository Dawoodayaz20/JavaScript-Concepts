For a Full-Stack / JS interview, they will test you in 4 layers. Don't just learn syntax, learn _why it breaks_.

### Layer 1: Core JS - 70% of questions come from here:

- Closures & Lexical Scope*: stale closures in `useEffect`, private variables

- *Hoisting*: `var` vs `let/const` vs `function`. `let` is hoisted but in TDZ

- *this* -> 4 rules: default, implicit, explicit (call/apply/bind), new. Arrow functions don't have their own `this`

- *Event Loop* -> This is THE question. 
* Call Stack -> Web APIs -> Microtask Queue (Promise, queueMicrotask) -> Macrotask Queue (setTimeout, setInterval). Microtasks always run first.
  
  ```javascript
  console.log(1)
  setTimeout(()=> console.log(2), 0)
  Promise.resolve().then(()=> console.log(3))
  console.log(4)
  // 1,4,3,2*-
  ```

- Prototypes & Inheritance* -> `*proto*` vs `prototype`, prototypal chain*- Equality* -> `==` vs `===`, coercion tricks `[] == ![]`*- var vs let vs const* -> scoping, re-declaration, hoisting

### *Layer 2: Modern JS & Async - Where seniors fail*

- *Promises vs async/await* -> states, chaining, error handling

- *Promise Methods* -> `Promise.all` (fails fast), `allSettled` (never fails), `race`, `any`

- *Debounce vs Throttle* -> search input = debounce, scroll/resize = throttle. Be ready to CODE them.

- *Currying & Composition* -> `const add = a => b => a+b`*- Spread, Rest, Destructuring* and shallow vs deep copy (`structuredClone`)

### *Layer 3: React / http://Next.js Specific - For Full-Stack*

- **Reconciliation & Virtual DOM**

- **Hooks Deep Dive**: `useEffect` cleanup, dependency array lies, `useMemo` vs `useCallback` vs `memo`

- **useRef vs useState**- SSR vs CSR vs SSG vs ISR* in http://Next.js - when to use what

- *Hydration Errors* -> why they happen on iPhone

- *Performance:* code splitting, `dynamic()`, lazy loading

### *Layer 4: Full-Stack Backend JS*

- *Node Event Loop & Clustering* -> Node is single-threaded
- *Closures for Module Pattern / Singleton
- **EventEmitter, Streams, Buffer**- REST vs GraphQL status codes
- **JWT vs Session, CORS, Cookies (httpOnly, SameSite)**- SQL vs NoSQL tradeoffs, Indexing, N+1 query*

### *Must-Code-In-Interview Topics (they WILL ask you to write):*

1. Polyfill for `bind`, `Promise.all`, `debounce`, `throttle`, `Array.map`
2. Flatten an array / deep flatten object
3. Implement currying: `sum(1)(2)(3)`
4. Output-based: `this`, event loop, closure loop bug

### *Pro tip to crack it:*

Don't say definition. Say definition + 1-line example + 1 bug it causes.

Bad: "Closure is function inside function"Good: "Closure is function remembering its lexical env after outer dies, causes stale state in React if dep array is wrong"

Want me to start a mock? I'll ask you 10 questions exactly like FAANG does - starting with Event Loop and Closures.
