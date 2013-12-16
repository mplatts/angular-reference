## Scope

### Inheritance
[Good explanation](http://stackoverflow.com/questions/14049480/what-are-the-nuances-of-scope-prototypal-prototypical-inheritance-in-angularjs/14049482)

**Primitive values aren't read from prototype...created fresh on scope**
~~~javascript
childScope.aString = 'child string'
~~~
![primitives](http://i.stack.imgur.com/OyVPW.png)

~~~javascript
childScope.anArray[1] = '22'
childScope.anObject.property1 = 'child prop1'
~~~
**Values of objects are read from prototype (if doesn't exist on scope)**
![from objects](http://i.stack.imgur.com/2QceU.png)

### $watch

**With an expression**

The first argument is an expression. This means it evaluates to something...so `1+1` is an expression - it evaluates to `2`. Or we can reference a variable, say `name`, which will evaluate to the value of the `name` variable.

![skitched-20131215-150457](https://f.cloud.github.com/assets/184383/1750534/43afccc4-659a-11e3-9e13-5662b4cfb919.jpg)

**With a function**

~~~javascript
$scope.fullName = function(){ 
  return $scope.person.firstName + ' ' + $scope.person.lastName;
}

$scope.$watch( fullName, function(){ console.log('name changed')} );
~~~