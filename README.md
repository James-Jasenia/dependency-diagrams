# Dependency Diagrams
#### References:
Essential Developer - Caio and Mike

# Example
![Dependency Diagram](/DependencyDiagram.png)

# Interpreting
### Solid line, empty head = "Inherits from" / "Is a"
This denotes that a class is inheriting from another class. In the example above, the NewsFeedViewConroller is inheriting from UIViewController, a class within the UIKit module. In this specific example, it is highlighting a modular dependency upon UIKit.

```
import UIKit

class NewsFeedViewController: UIViewController {}
```
![Inherits From](/InheritsFrom.png)


- Is a
- Implements
- Depends on
