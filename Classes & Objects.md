A **class** is a _blueprint_, _template_, or _recipe_ for creating objects. It defines **what an object will contain** (its data) and **what it will be able to do** (its behavior).

```java
public class Car {
    // Attributes
    private String brand;
    private String model;
    private int speed;

    // Constructor
    public Car(String brand, String model) {
        this.brand = brand;
        this.model = model;
        this.speed = 0;
    }

    // Method to accelerate
    public void accelerate(int increment) {
        speed += increment;
    }

    // Method to display info
    public void displayStatus() {
        System.out.println(brand + " is running at " + speed + " km/h.");
    }
}
```
```cpp
class Car {
private:
    // Attributes
    string brand;
    string model;
    int speed;

public:
    // Constructor
    Car(const string& brand, const string& model) 
        : brand(brand), model(model), speed(0) {
    }

    // Method to accelerate
    void accelerate(int increment) {
        speed += increment;
    }

    // Method to display info
    void displayStatus() const {
        cout << brand << " is running at " << speed << " km/h." << endl;
    }
};
```
```python
class Car:
    # Constructor
    def __init__(self, brand, model):
        # Attributes (private by convention with underscore)
        self._brand = brand
        self._model = model
        self._speed = 0

    # Method to accelerate
    def accelerate(self, increment):
        self._speed += increment

    # Method to display info
    def display_status(self):
        print(f"{self._brand} is running at {self._speed} km/h.")
```

## __ENUMS__
An **enum** (short for enumeration) is a special data type that defines a fixed set of named constants. Unlike strings or integers, enums are **type-safe**, meaning the compiler ensures you can only use values that actually exist in your defined set.