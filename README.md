
# Food Recommendation Ontology / Logical-Programming

## Table of Contents
- [Overview](#overview)
- [Installation and Usage](#installation-and-usage)
- [Features](#features)
- [Technical Details](#technical-details)
  - [Key Classes](#key-classes)
  - [Applying Disjoint Classes](#applying-disjoint-classes)
  - [Relationships Between Classes](#relationships-between-classes)
  - [Assigning Domain and Range to Object Properties](#assigning-domain-and-range-to-object-properties)
  - [Data Properties and Relations](#data-properties-and-relations)
  - [Property Restrictions](#property-restrictions)
  - [Applying Closure Axiom](#applying-closure-axiom)
  - [Changing a Primitive Class to a Defined Class](#changing-a-primitive-class-to-a-defined-class)
  - [Using the Reasoner](#using-the-reasoner)

- [Applications](#applications)
- [Examples](#examples)
- [Conclusion](#conclusion)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)













## Overview
This repository contains a comprehensive food ontology written in OWL (Web Ontology Language). It aims to provide a standardized vocabulary and semantic structure for describing food products, ingredients, personalized nutritional recommendations to support healthy eating through a comprehensive food ontology and related concepts.
<div style="display: flex; justify-content: space-around;">
    <img src="Technical_Details/Details_Pics/metrics_pic1.png" alt="Image 1" width="32%">
    <img src="Technical_Details/Details_Pics/metrics_pic2.png" alt="Image 2" width="33%">
    <img src="Technical_Details/Details_Pics/metrics_pic3.png" alt="Image 3" width="28%">
</div>

<img src="Images/all.png" alt="Overview of the project" width="40%">

## Installation and Usage
The ontology can answer various queries, including:
- Written in OWL (Web Ontology Language)
- Developed using Protégé [5.5.0]
- Installation and Usage: (https://protege.stanford.edu)

## Features

## Technical Details
### Key Classes
- **Dish**: Represents a dish made from various ingredients.
- **Ingredient**: Classifies ingredients into animal-based and plant-based categories.
- **Nutrition**: Includes subclasses for carbohydrates, fats, fibers, proteins, minerals, and vitamins.
- **User**: Represents user preferences and dietary restrictions.
- **Disease**: Classifies various diseases that may affect dietary recommendations.
<img src="Images/class_pic1.png" alt="Overview of the project" width="40%">

### Applying Disjoint Classes
- Classes that cannot overlap:
  - Example: Vitamin and carbohydrate are disjoint, meaning an instance cannot be both.
<img src="Images/Disjoint_pic.png" alt="Overview of the project" width="40%">

### Relationships Between Classes
- **hasIngredient**: Links dishes to their ingredients.
- **hasNutrient**: Connects ingredients to their nutritional content.
- **servedAsMeal**: Specifies when a dish can be served (e.g., breakfast, lunch, dinner).

### Assigning Domain and Range to Object Properties
| Object Property       | Domains         | Ranges         | Characteristics     |
|-----------------------|-----------------|-----------------|----------------------|
| hasIngredient         | Dish            | Ingredient      |                      |
| isIngredientOf        | Ingredient      | Dish            | Inverse Relationship  |
| hasNutrient           | Ingredients     | Nutrition       | Transitive           |
| hasSpicyLevel         | Dish            | Level_Of_Spicy | Functional           |

### Data Properties and Relations
| Top Data Properties    | Characteristic | Type    |
|------------------------|----------------|---------|
| hasCalorieValue        | Functional     | Integer |
| hasSaltAmountGram      | Functional     | Integer |
| hasSugarAmountGram     | Functional     | Integer |

### Property Restrictions
Utilizes property restrictions like existential and universal quantifiers to define complex dishes, vegan dishes, and more.
- **Complex_Dish**: Dish and (hasIngredient min 10 owl:Thing)
- **VeganDish**: Dish and (hasIngredient only PlantBasedIngredient)
- **HighProteinDish**: Dish and ((hasIngredient some Bean) or (hasIngredient some Chickpea) or (hasIngredient some Lentil) or (hasIngredient some Quinoa))

### Relationships
- **hasIngredient**: Connects dishes to their ingredients.
- **hasNutrient**: Links ingredients to their nutritional content.
- **servedAsMeal**: Specifies when a dish can be served (e.g., breakfast, lunch, dinner).

### Applying Closure Axiom
- Example: Hummus can only be made with Chickpea, Olive oil, Pepper, and Salt.

### Changing a Primitive Class to a Defined Class
- By adding sufficient conditions to necessary conditions, a primitive class can be transformed into a defined class.

### Using the Reasoner
- The reasoner checks the consistency of statements and definitions in the ontology and helps maintain the hierarchy.

### Visual Representations
- Include relevant images or diagrams to illustrate the relationships and class structures.








## Property Restrictions


## Applications
The ontology can be applied in various domains, including restaurants, the food industry, and domestic settings.

## Examples
Expected queries to be answered, such as:
- Recommend the user dishes based on the ingredients
- Recommend the user dishes based on the nutrition.
- Recommend the user dishes based on amount of calorie.
- Recommend the user dishes based on different categories such as, high protein dishes, vegan dishes, complex dishes, and different meals.
- Recommend the user dishes based on their allergy.
- Recommend the user dishes based on their disease.

## Authors and Contributions
This project builds on works by several authors, including Dooley et al., and utilizes methodologies from Horridge et al. and Neuhaus & Brodaric.

## Conclusion
The Food Recommendation Ontology is a versatile tool for suggesting dishes that meet users' nutritional needs and preferences, promoting healthier eating habits.
 
## Contributing
[Guidelines for contributing to the project]

## License
This project is licensed under [specify license].

## Contact
For questions or feedback, please contact [your contact information].














