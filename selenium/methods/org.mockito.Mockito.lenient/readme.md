### What is `UnnecessaryStubbingException` in Mockito?

By default, Mockito 3.0+ enable strict strubbing. Strict stubbing ensures that redundant test code is minimal by raising an exception - `UnnecessaryStubbingException`, when an unused stub is declared or a stub is declared twice.


#### Examples

```java
Mockito.when(mockObject.someMethod()).thenReturn(1);
Mockito.when(mockObject.someMethod()).thenReturn(2);
```
In the code above, the `someMethod` is stubbed twice, which is unnecessary and would trigger the UnnecessaryStubbingException. To avoid this, you should only stub a method once and only if it's necessary for your test case.

```java
MyClass mockObject = Mockito.mock(MyClass.class);
Mockito.when(mockObject.someMethod()).thenReturn(1);
```

In this code, the method `someMethod` is stubbed, but it's not called in the test case. This results in an unused stub, and causes the exception to be raised.

### What is lenient stubbing?

To bypass strict stubbing, stubs can be configured as `lenient` which will not raise the exception. These stubs won't be checked for potential stubbing problems, such as the unnecessary stubbing.

#### Example

```java
MyClass mockObject = Mockito.mock(MyClass.class, Mockito.RETURNS_SMART_NULLS);
Mockito.lenient().when(mockObject.someMethod()).thenReturn(1);
```

In this example, mockObject is created as a lenient mock. This bypasses the strict stubbing checks.

Keep in mind that lenient mocks should be used with caution, as they can hide potential problems in your test code. It's best to use strict mocks (the default behavior in Mockito) and only use lenient mocks if necessary.