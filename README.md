# plp-python-5
Let’s create a class to represent a **Superhero**. This example will include attributes like name, power, and level, along with methods for actions like **attack** and **defend**. We’ll then add inheritance to create a **Supervillain** class, demonstrating polymorphism and encapsulation.

### Code:

```python
# Base class for Superhero
class Superhero:
    def __init__(self, name, power, level):
        self.name = name  # Name of the superhero
        self.power = power  # Power of the superhero (e.g., "flight", "strength")
        self.level = level  # Level of the superhero (1-10)

    def attack(self):
        print(f"{self.name} attacks with {self.power}!")

    def defend(self):
        print(f"{self.name} defends with {self.power}!")

    def show_info(self):
        print(f"Superhero: {self.name}")
        print(f"Power: {self.power}")
        print(f"Level: {self.level}")

# Inherited class for Supervillain, demonstrating Polymorphism
class Supervillain(Superhero):
    def __init__(self, name, power, level, weakness):
        # Calling the parent class constructor
        super().__init__(name, power, level)
        self.weakness = weakness  # A new attribute for weakness

    def attack(self):
        # Overriding the attack method to change behavior for Supervillain
        print(f"{self.name} attacks with {self.power} and uses evil tactics!")

    def show_info(self):
        super().show_info()  # Call the parent method to show superhero info
        print(f"Weakness: {self.weakness}")  # Show the villain's weakness

    def taunt(self):
        print(f"{self.name} laughs menacingly: 'You can't stop me!'")

# Example Usage
hero = Superhero("Captain Valor", "strength", 8)
villain = Supervillain("Dr. Doom", "mind control", 9, "lightning")

# Showing info
hero.show_info()
villain.show_info()

# Attacks and Defends
hero.attack()
villain.attack()

# Defending and Taunting
hero.defend()
villain.taunt()
```

### Explanation:
1. **Superhero Class**:
   - **Attributes**: The `Superhero` class has attributes `name`, `power`, and `level`, initialized through the constructor.
   - **Methods**: The `attack` and `defend` methods describe actions the superhero can take. The `show_info` method prints the superhero's details.

2. **Supervillain Class**:
   - **Inheritance**: `Supervillain` inherits from `Superhero`, which means it can use all the attributes and methods from the `Superhero` class.
   - **Polymorphism**: The `Supervillain` class overrides the `attack` method to change how the villain attacks compared to the superhero.
   - **Encapsulation**: The villain has a new attribute `weakness` and a new method `taunt` that’s specific to the villain class.

3. **Demonstrating Polymorphism**: 
   - The `attack` method is defined in both the `Superhero` and `Supervillain` classes, but each class has its own implementation of how the attack works.

4. **Demonstrating Inheritance**:
   - `Supervillain` inherits all attributes and methods from `Superhero` and extends them by adding the `weakness` attribute and the `taunt` method.

### Example Output:

```
Superhero: Captain Valor
Power: strength
Level: 8
Supervillain: Dr. Doom
Power: mind control
Level: 9
Weakness: lightning
Captain Valor attacks with strength!
Dr. Doom attacks with mind control and uses evil tactics!
Captain Valor defends with strength!
Dr. Doom laughs menacingly: 'You can't stop me!'
```

### Key Concepts Demonstrated:
1. **Encapsulation**: The attributes of `Superhero` and `Supervillain` (like `weakness` for villains) are encapsulated within their respective classes.
2. **Inheritance**: `Supervillain` inherits the properties and methods of `Superhero`, and can extend or modify behavior.
3. **Polymorphism**: The `attack` method is defined in both the `Superhero` and `Supervillain` classes, but they have different implementations.
