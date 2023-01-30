### What is mockconstruction in Mockito?

With the mockConstruction you can mock calls made to the constructor. Let us illustrate this with an example:

```java
class Car {
    public Car() {}
    public String makeSound() {return "Vroom";}
}

@Test
void mockingConstructor() {

    // Scope of constructor mocking
    try (MockedConstruction<Car> mock = mockConstruction(Car.class)) {
        // creating a mock instance
        Car car = new Car();
        when(car.makeSound()).thenReturn("Weee");

        assertThat(car.makeSound()).isEqualTo("Weee");

        // Get a list of all created mocks
        List<Car> constructed = mock.constructed();
        assertThat(constructed).hasSize(1);
    }
    
    // Normal Car instance that is not mocked
    assertThat(new Car().makeSound()).isEqualTo("Vroom");

}
```

We mock the Car class's constructor, which is called from the test code. Within a try statement, we limit the scope to prevent any further calls to the constructor. When your code calls the constructor inside this try statement, it returns a mock object. Outside that try statement, calls to the class's constructor will not be mocked by Mockito. This example also works when you mock a private constructor. If the Car class had a private constructor, calls to it would still succeed outside of our try-with-resources statement.
