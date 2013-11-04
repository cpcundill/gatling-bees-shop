Gatling Stress Tool
==============

Make fun with Gatling on bees-shop webapp (from Cloudbees)

Links
-------

- Github (code source): https://github.com/excilys/gatling/
- DSL: http://gatling-tool.org/cheat-sheet/
- Links: https://github.com/excilys/gatling/wiki/Links

Hand's On
-------

### Running Bees Shop

    mvn clean tomcat7:run
    
Visit the bees shop : [here](http://localhost:8080/gatling-bees-shop/ "here")

Browse the site to see what kinds of products are sold (*Djerba Style?*)

### TODO #1: Scenario 'View 5 random products'

***!!! Check that the server respond 200 for each request !!!***

Code the scenario **[ConsultProductsScenario.scala](https://github.com/clardeur/gatling-bees-shop/blob/xke-workshop/src/test/scala/ConsultProductsScenario.scala "ConsultProductsScenario")** :
- view the home page (@see https://github.com/excilys/gatling/wiki/HTTP#wiki-method)
- view the list of products
- view 5 random products (@see https://github.com/excilys/gatling/wiki/Feeders and https://github.com/excilys/gatling/wiki/Structure-Elements#wiki-repeat)

### TODO #2: Setup the simulation with a scenario

Setup a simulation with the previous created scenario **[BeesShopSimulation.scala](https://github.com/clardeur/gatling-bees-shop/blob/xke-workshop/src/test/scala/BeesShopSimulation.scala "BeesShopSimulation.scala")** :

- make a simulation with 100 users at once (@see https://github.com/excilys/gatling/wiki/Gatling%202#wiki-inject)
- play with different types of injection

For more information on injection possibilities 'http://blog.roddet.com/2013/06/gatling2-new-inject-api/'

### TODO #3: Scenario 'Search and comment a product'

Code the scenario **[SearchAndCommentProductsScenario.scala](https://github.com/clardeur/gatling-bees-shop/blob/xke-workshop/src/test/scala/SearchAndCommentProductsScenario.scala "SearchAndCommentProductsScenario.scala")** :
- view the home page
- search a random product by name (@see https://github.com/excilys/gatling/wiki/HTTP#wiki-query-params) 
- view a product found in the search randomly (@see https://github.com/excilys/gatling/wiki/Session to saveAs() the product ID found in the searh result list)
- add a comment to this product (@see https://github.com/excilys/gatling/wiki/HTTP#wiki-post-parameters)

### TODO #4: Scenario 'Add 3 products in cart'

Code the scenario **[AddProductsInCartScenario.scala](https://github.com/clardeur/gatling-bees-shop/blob/xke-workshop/src/test/scala/AddProductsInCartScenario.scala "AddProductsInCartScenario.scala")** :
- view the home page and verify that the cart is empty
- randomly view a product as long as the number of products in the cart is not 3
  - 30% chance to add a product into the cart when consulting it
  - else pause 1 to 5 seconds on it

Jenkins Plugin
-------

Demonstration of the Gatling plugin on Jenkins.

https://wiki.jenkins-ci.org/display/JENKINS/Gatling+Plugin



