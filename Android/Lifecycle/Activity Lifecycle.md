------

## 1.  생명주기

### 1 - 1. 생명주기란?

![img](https://t1.daumcdn.net/cfile/tistory/9917D03D5E73735E29)

사람이 태어나서 죽는 과정이 있듯이 액티비티 또한 생성되고 제거되는 과정이 있다.

생명주기를 이해하고 때에 맞는 적절한 작업을 하면 안정적인 앱을 만들 수 있다.

그렇지 않으면 발생하는 대표적인 사례는 다음과 같다.

### 1. 앱을 사용하다가 다른 앱으로 전환 할 때 강제 종료되는 경우

: 유튜브 보다가 공유하기를 눌러서 카카오톡을 켰는데 유튜브가 강제로 종료 되는 상황

### **2. 앱을 사용하고 있지 않은데 리소스가 낭비되는 경우**

: 산속에서 GPS를 잡다가 안되서 포기하고 잠금 상태로 두었다고 치자.

그리고 나중에 다시 폰을 켜보니 앱이 계속 GPS를 잡는다고 배터리를 다 사용했다고 상상해보자

### **3. 앱에서 나갔다가 다시 들어왔는데 사용자의 진행 상태가 저장되지 않은 경우**

: 게임 다운로드가 너무 오래 걸려서 잠시 카톡 보내고 왔는데 다시 처음부터 받아야 한다고 상상해보자

### **4. 화면 가로/세로 전환을 할 경우, 강제 종료되거나 진행 상태가 저장되지 않은 경우**

: 누워서 웹툰보다가 반대쪽으로 돌아누웠는데 앱이 갑자기 꺼졌다고 상상해보자

생명 주기를 고려하지 않고 앱을 만들면 충분히 생길 수 있는 상황이다.

### **1-2. onCreate**

```kotlin
class MainActivity : AppCompatActivity() {
 
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
    }
}
```

우리가 액티비티를 새로 생성하면 클래스 안에 onCreate가 자동으로 생성되어 있는 것을 볼 수 있다.

다른 메서드는 없는데 onCreate만!

그 말은 즉슨 반드시 구현해야 하는 메서드란 뜻이다.

onCreate는 액티비티가 생성되면 가장 먼저 실행되는 메서드이다.

화면 레이아웃 정의,  뷰를 생성하거나 데이터 바인딩 등을 이곳에서 하면 된다.

그리고 생명주기 동안 딱 한 번만 실행되는 메서드이기도 하다.

그래서 액티비티 최초 실행 시에만 해야할 작업을 여기서 하면 된다.

### **1-3. onStart**

액티비티가 화면에 표시되기 직전에 호출된다.

**화면에 진입할 때마다 실행되어야 하는 코드**를 이곳에 작성하면 된다.

### ***\*1-4. onResume\****

다른 액티비티가 액티비티를 덮어버리거나

앱 사용 중 전화가 와서 잠시 앱을 떠나거나

카톡에서 사진 첨부할 때 '갤러리'가 아닌 '카메라'를 클릭해 카메라를 켠다거나 등의 상황으로

잠시 액티비티가 **일시정지 되었다가 돌아오는 경우** onResume 메서드가 호출된다.

만약 액티비티가 **재개되었을 때 실행해야 할 코드**가 있다면 이곳에 작성하면 된다.

onStart에서 초기화 작업을 했다면 -> onStop에서 리소스 해제/종료 작업을 하고

onResume에서 초기화 작업을 했다면 -> onPause에서 리소스 해제/종료 작업을 해야한다.

이걸 염두에 두고 코드를 작성하면 될 것 같다.

### **1-5. onPause**

방금 앞서 말했듯 방해되는 이벤트가 발생하면 이 메서드가 호출된다.

즉, 사용자가 액티비티를 잠시 떠나기 때문에

리소스를 계속 소모하거나 GPS가 계속 작동하거나 이럴 필요가 없는 것이다.

**포그라운드에 있지 않을 때 실행할 필요가 없는** **기능**들을 onPause에서 **일시 정지하면** 된다.

종료되기 전에 호출되는 메서드가 onStop, onDestroy 이렇게 2개가 더 있어서

여기서 작업해도 되지 않을까 라는 생각이 들지만

onStop, onDestroy는 메모리가 부족하면 호출되지 않을 수 있다는 문제가 있다.

onPause()는 아주 잠깐 실행되는 메서드 이므로

데이터를 저장, 네트워크 호출 등 무거운 작업  ❌

무거운 작업은 바로 다음에 설명할 onStop에서 하면 된다.

### 1-6. onStop

액티비티가 사용자에게 더 이상 보이지 않으면 이 메서드가 호출 된다.

앞서 말했듯이 무거운 작업을 이곳에서 해주면 된다.

### **1-7. onRestart**

홈으로 나갔다가 다시 돌아오거나

다른 액티비티로 갔다가 뒤로 가기 버튼을 통해서 돌아오는 경우 이 메서드가 호출된다.

### **1-8. onDestroy**

앱을 종료하는 경우 호출된다.

onStop에서 혹시 아직 해제하지 못한 리소스 작업을 하면 되는데

앞서 말했듯이 메모리가 부족하면 메서드 호출이 이루어지지 않고 종료될 수 있다는 것에 유의해야 한다.

| 액티비티 상태 | 종료될 확률 |
| ------------- | ----------- |
| Created       |             |
| Started       |             |
| Resumed       | 낮음        |
| Paused        | 중간        |
| Stoped        |             |
| Destroyed     | 높음        |

## 2.  실행

### 2-1. 앱 실행

onCreate - onStart - onResume

### 2-2. 홈 화면

onPause - onStop

### 2-3. 홈 → 앱

onRestart - onStart - onResume

### 2-4. 앱 종료

onPause - onStop

### 2-5. 첫 번째 액티비티 → 두 번째 액티비티

onPause - onCreate - onStrart - onResume - onStop

### 2-6. 두 번째 액티비티 →  첫 번째 액티비티

**onPause** - **onRestart** - **onStart** - **onResume** - **onStop** - **onDestroy**

## 3. 실습 코드

[Activity Lifecycle](https://github.com/yeon0821/AndroidStudy/blob/main/Lifecycle_Test/app/src/main/java/Activity/MainActivity.kt)