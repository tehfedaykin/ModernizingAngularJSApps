### Async Pipe

Creates a subscription in the template +<br /> unsubscribes when component is destroyed.

```html
<ul class="queens">
  <li ng-repeat="queen in (vm.displayedQueens$ | async)">
    <a href="#!/queens/{{queen.id}}">{{queen.name}}</a>
    <p>{{queen.quote}}</p>
  </li>
</ul>
```