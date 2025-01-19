# Pizza-Ontology
Pizza Ontology Project

# Pizza Ontology

## Overview
The **Pizza Ontology** is a semantic representation of pizzas, toppings, and wine pairings. This project leverages description logic and ontology design principles to model the relationships between pizzas, their ingredients, and recommended wine pairings. The ontology is suitable for reasoning tasks, querying, and educational purposes in the field of knowledge engineering.

---

## Features
- **Hierarchical Class Structure**: Organizes pizzas into classes and subclasses, such as `VegetarianPizza` and `MeatPizza`.
- **Topping Classification**: Categorizes toppings into `CheeseTopping`, `MeatTopping`, and `VegetableTopping`.
- **Wine Pairings**: Maps pizzas to their recommended wines for an enriched dining experience.
- **Logical Axioms**: Ensures consistency and facilitates reasoning through properties like `hasTopping` and `recommendedWine`.

---

## Classes and Subclasses
### Pizza
- `Pizza` (Root Class)
  - `VegetarianPizza`
  - `MeatPizza`
  - `MargheritaPizza`
  - `PepperoniPizza`
  - `FourCheesePizza`

### Topping
- `Topping` (Root Class)
  - `CheeseTopping`
    - `MozzarellaTopping`
    - `ParmesanTopping`
    - `GorgonzolaTopping`
  - `MeatTopping`
    - `PepperoniTopping`
    - `HamTopping`
  - `VegetableTopping`
    - `TomatoTopping`
    - `MushroomTopping`
    - `OliveTopping`

### Wine
- `Wine`
  - `Chianti`
  - `SauvignonBlanc`
  - `Prosecco`
  - `PinotGrigio`
  - `Malbec`
  - `Chardonnay`
  - `Merlot`

---

## Properties (Roles)
### Object Properties
- **`hasTopping`**: Relates a `Pizza` to one or more `Topping`.
- **`recommendedWine`**: Relates a `Pizza` to one or more `Wine`.
- **`isToppingOf`**: The inverse of `hasTopping`.

### Data Properties
- **`wineNotes`**: Provides descriptive notes about a wine’s flavor profile.

---

## Logical Axioms
- **Pizza Definition**:
  ```
  Pizza ≡ ∃hasTopping.Topping
  ```
  A pizza must have at least one topping.

- **Vegetarian Pizza**:
  ```
  VegetarianPizza ≡ Pizza ⊓ ¬∃hasTopping.MeatTopping
  ```
  A vegetarian pizza does not contain meat toppings.

- **Wine Pairing Example**:
  ```
  recommendedWine(PepperoniPizza, Malbec)
  ```

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/pizza-ontology.git
   ```
2. Open the ontology file (`pizza-ontology.owl`) in [Protégé](https://protege.stanford.edu/).

---

## Usage
1. **Reasoning**: Use a reasoner (e.g., HermiT) in Protégé to infer class memberships and validate consistency.
2. **Querying**: Perform SPARQL queries to retrieve information, such as:
   - "What wines are recommended for Vegetarian Pizzas?"
   - "Which toppings are used in Pepperoni Pizzas?"

---

## Example SPARQL Query
Retrieve recommended wines for each type of pizza:
```sparql
SELECT ?pizza ?wine
WHERE {
  ?pizza rdf:type :Pizza .
  ?pizza :recommendedWine ?wine .
}
```

---

## Contributing
Contributions are welcome! Please:
1. Fork the repository.
2. Create a feature branch.
3. Submit a pull request with a clear description of your changes.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments
- Developed using [Protégé](https://protege.stanford.edu/) and OWL.
- Inspired by culinary arts and semantic technologies.

---

## Contact
For questions or feedback, reach out at **ivam.developer@gmail.com** or open an issue in this repository.


