## Directives

Examples come mostly from egghead.io but with some diagrams added by me.
Just quicker to scan this then re-watch his videos.

!(Angular Directives)[https://github.com/angular/angular.js/tree/30a8b7d0b5d4882c2bf3b20eb696a02f5b667726/src/ng/directive]

### Using element attributes

**From link**

Reference the 'attrs' parameter you receive in the 'link' function.

~~~html
<div ng-app="drinkApp">
  <div ng-controller="AppCtrl">
    <div drink flavor="strawberry"></div>
  </div>
</div>

<script>
var app = angular.module('drinkApp', []);
 
app.controller("AppCtrl", function ($scope) {
})
 
app.directive("drink", function () {
  return {
    scope: {},
    template: '<div>{{ flavor }}</div>',
    link: function (scope, element, attrs) {
      scope.flavor = attrs.flavor;
    }
  };
});
</script>
~~~

**Using scope**

~~~html
<div ng-app="drinkApp">
  <div ng-controller="AppCtrl">
    <div drink flavor="strawberry"></div>
  </div>
</div>

<script>
var app = angular.module('drinkApp', []);
 
app.controller("AppCtrl", function ($scope) {
})
 
app.directive("drink", function () {
  return {
    scope: {
      flavor: '@'
    },
    template: '<div>{{ flavor }}</div>'
  };
});
</script>
~~~

![skitched-20131213-082034](https://f.cloud.github.com/assets/184383/1740651/70eb0d42-63cf-11e3-92b1-bf45ba170b4c.jpg)
