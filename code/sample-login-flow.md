### Sample Login Flow

```typescript
function LoginCtrl(UserService: any, AuthService: any) {
  ...

  //subscribe to user member on service to get current state
  UserService.getUser().subscribe((val:User) => {
    vm.user = val;
  });

  vm.submitForm = function(){
    AuthService.logIn(vm.form).subscribe((res: fakeResponse<User>) => {
      //upon successful login set state to have user profile
      UserService.setUser(res.data)
    })
  }

  vm.logOut = function() {
    AuthService.logOut().subscribe(() => {
      UserService.removeUser();
    })
  }
}
```