### User State Service

```typescript
import { BehaviorSubject, Observable } from "rxjs";

function userService() {
  const userState = new BehaviorSubject<null | User>(null)

  return {
    getUser: getUser,
    setUser: setUser,
    removeUser: removeUser
  }

  function getUser(): Observable<User> {
    return userState;
  }

  function setUser(user: User) {
    userState.next(user);
  }

  function removeUser() {
    userState.next(null);
  }

}

export default userService;
```