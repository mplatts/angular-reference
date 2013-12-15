## Scope

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