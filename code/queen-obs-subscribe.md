### Subscribe to Observable in Template

```html
<ul class="queens">
  <li ng-repeat="queen in (vm.displayedQueens$ | async:this)">
    <a href="#!/queens/{{queen.id}}">{{queen.name}}</a>
    <p>{{queen.quote}}</p>
  </li>
</ul>
```