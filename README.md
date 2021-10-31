# Dependency Diagrams
#### References:
Essential Developer - Caio and Mike

# Example
![Dependency Diagram](/DependencyDiagram.png)

# Interpreting
### Solid line, empty head = "Inherits from" / "Is a"
This denotes that a class is inheriting from another class. In the example below, the NewsFeedViewConroller is inheriting from UIViewController, a class within the UIKit module. In this specific example, it is highlighting a modular dependency upon UIKit.

```
import UIKit

class NewsFeedViewController: UIViewController {}
```

![Inherits From](/InheritsFrom.png)


### Solid line, closed head = "Strong dependency on" / "Has a"
This denotes that a class has an instance of another class that is created upon point of initialisation or is injected. It is best practice to inject this dependency using property or constructor injection.

```
class NewsFeedVieController {

  private let loader: NewsFeedAPI
  
  init(loader: NewsFeedAPI) {
    self.loader = loader 
   }
}
```

![Depends On](/DependsOn.png)

### Dashed line, open head = "Conforms to" / "Implements"
This denotes that a class conforms to or implements a protocol/interface. In the example below, the NewsFeedAPI implements the APIService protocol.

class NewsFeedAPI: APIService {

  //Protocol Methods.

}

- Is a
- Implements

