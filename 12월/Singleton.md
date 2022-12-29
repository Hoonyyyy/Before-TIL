
## Singleton: 특정 클래스의 인스턴스가 오직 하나임을 보장하는 객체

```swift
// "static"을 이용해 "instance"를 저장할 "프로퍼티"를 하나 생성해주기
// "init" 함수 접근제어자를 "private"로 저장하기
// "init()" 함수를 호출해 "instance"를 또 생성하는 것을 막기 위해 init() 함수 접근 제어자를
// "private"로 지정해주기
class UserInfo {
    static let shared = UserInfo()

    var id: String?
    var password: String?
    var name: String?
    
    private init() { }
}

// A 뷰 컨트롤러
let userInfo = UserInfo.shared
userInfo.id = "myId"

UserInfo.shared.id

// B 뷰 컨트롤러
let userInfo = UserInfo.shared
userInfo.password = "myPwd123"

UserInfo.shared.password

// C 뷰 컨트롤러
let userInfo = UserInfo.shared
userInfo.name = "myName"

UserInfo.shared.name

```
