# Dependency Diagrams
#### References:
Essential Developer - Caio and Mike

![Dependency Diagram](/DependencyDiagramExample.png)
<br />
<br />
<br />
<br />
# Solid line, empty head = "Inherits from" / "Is a"
<br />
![Inherits From](/InheritsFrom.png)
<br />
This denotes that a class is inheriting from another class. In the example below, the NewsFeedViewConroller is inheriting from UIViewController, a class within the UIKit module. In this specific example, it is highlighting a modular dependency upon UIKit.

```
import UIKit

class NewsFeedViewController: UIViewController {}
```
<br />
<br />
<br />

# Solid line, closed head = "Strong dependency on" / "Has a"
<br />
![Depends On](/DependsOn.png)
<br />
This denotes that a class has an instance of another class that is created upon point of initialisation or is injected. It is best practice to inject this dependency using property or constructor injection.

```
class NewsFeedVieController {

  private let loader: NewsFeedAPI
  
  init(loader: NewsFeedAPI) {
    self.loader = loader 
   }
}
```
<br />
<br />
<br />
# Dashed line, open head = "Conforms to" / "Implements"
<br />
![Depends On](/ConformsTo.png)
<br />
This denotes that a class conforms to or implements a protocol/interface. In the example below, the APIService implements the NewsFeedAPI protocol.
```
class APIService: NewsFeedAPI {

  //Protocol Methods.

}
```
<br />
<br />
<br />
### Dashed line, filled head = "Weakly depends on"
<br />
![Depends On](/WeaklyDependsOn.png)
<br />
This denotes a weak dependency on another object. This is commonly seen in dependency that are passed straight to methods but not stored as properties in the containing class. In the example below, the APIService can be initialised without any strong concrete dependencies, however, the class itself has a weak dependency upon HTTPClient as it is required for one of it's methods. I don't like this approach as it is an implicit dependency. 
```
class APIService {

  func load(using client: HTTPClient)
  
}

```
