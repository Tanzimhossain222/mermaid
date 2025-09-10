

```mermaid
flowchart TD
    A([Start]) --> B[/Input x/]
    B --> C{x > 5 ?}
    C -.- Yes --> D((End))
    C -- No --> F[/Print x/]
    F --> G[x += 1]
    G --> C
```