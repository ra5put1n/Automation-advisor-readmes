### What is `org.openqa.selenium.InvalidElementStateException`?

The `org.openqa.selenium.InvalidElementStateException` exception when the element that you are trying to interact with is not in a state where actions can be performed with it. For example, a readonly field which you are trying to access.

Such instances may arise when an element is being obscured by another element while clicking or the desired element perhaps is not being visible on the HTML DOM.


### Possible solution

You have to consider a few facts as follows :

Never mixup `implicitlyWait()` and `WebDriverWait()` as the documentation clearly mentions the following :

Do not mix implicit and explicit waits. Doing so can cause unpredictable wait times. For example setting an implicit wait of 10 seconds and an explicit wait of 15 seconds, could cause a timeout to occur after 20 seconds.

So you need to remove all the instances of `implicitlyWait()`.