# Dependency Diagrams
#### References:
Essential Developer - Caio and Mike

![Dependency Diagram](/DependencyDiagramExample.png)

# Solid line, empty head = "Inherits from" / "Is a"
![Inherits From](/InheritsFrom.png)
This denotes that a class is inheriting from another class. In the example below, the NewsFeedViewConroller is inheriting from UIViewController, a class within the UIKit module. In this specific example, it is highlighting a modular dependency upon UIKit.

```
import UIKit

class NewsFeedViewController: UIViewController {}
```

# Solid line, closed head = "Strong dependency on" / "Has a"
![Depends On](/DependsOn.png)
This denotes that a class has an instance of another class that is created upon point of initialisation or is injected. It is best practice to inject this dependency using property or constructor injection.

```
class NewsFeedVieController {

  private let loader: NewsFeedAPI
  
  init(loader: NewsFeedAPI) {
    self.loader = loader 
   }
}
```

# Dashed line, open head = "Conforms to" / "Implements"
![Depends On](/ConformsTo.png)
This denotes that a class conforms to or implements a protocol/interface. In the example below, the APIService implements the NewsFeedAPI protocol.
```
class APIService: NewsFeedAPI {

  //Protocol Methods.

}
```

### Dashed line, filled head = "Weakly depends on"


