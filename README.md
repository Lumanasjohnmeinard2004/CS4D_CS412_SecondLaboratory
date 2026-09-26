# CS4D_CS412_SecondLaboratory

# Adaptive Coding System Prototype

A simple adaptive coding environment that changes its interface and assistance based on the characteristics of different programming users.

This project was developed for the **CS412 User Modeling Laboratory Activity: From User Preferences to an Adaptive Coding Environment**.

The prototype focuses on demonstrating **user modeling and system adaptation** rather than recreating a complete Integrated Development Environment (IDE).

---

## Overview

Programmers have different levels of experience and different preferences when using coding environments.

A beginner may benefit from:

- More coding guidance
- Detailed feedback
- Learning-oriented explanations
- Formatting assistance
- Error explanations

An experienced developer may prefer:

- Fewer beginner prompts
- Concise feedback
- Less visual guidance
- Short and direct assistance

This prototype represents these differences using a **user model** and adapts the coding environment according to the selected user profile.

---

## Data Source

The user models were developed using information from the publicly available **Stack Overflow Developer Survey** dataset.

Dataset used:

```text
survey_results_public.csv
```

Relevant information considered from the dataset includes:

- Programming experience
- Years of coding experience
- Programming languages
- Development environments and tools
- AI tool usage
- Coding activities

The survey data was used to identify differences between programming users and to help construct the user profiles demonstrated by the prototype.

---

## User Profiles

The prototype contains two user profiles.

### Profile A - Beginner / Learner

Represents a programmer with less coding experience who receives more guidance from the system.

| Attribute | Value |
|---|---|
| Experience Level | Beginner / Learner |
| Years Coding | 0-5 years |
| Languages | Python, JavaScript |
| Coding Frequency | Occasional / Learning |
| Auto-completion | High |
| Auto-formatting | High |
| Error Detection | High |
| Debugging Assistance | High |
| AI Assistance | High |
| Guidance Level | High |

### Profile B - Experienced Developer

Represents an experienced programmer who receives more concise assistance and fewer beginner-oriented prompts.

| Attribute | Value |
|---|---|
| Experience Level | Experienced Professional |
| Years Coding | 10+ years |
| Languages | Python, JavaScript, TypeScript, etc. |
| Coding Frequency | Daily |
| Auto-completion | Moderate |
| Auto-formatting | Low |
| Error Detection | Moderate |
| Debugging Assistance | High |
| AI Assistance | High |
| Guidance Level | Low |

---

## Adaptive Behavior

The system reads the selected user profile and changes its behavior according to the attributes stored in the user model.

### Beginner / Learner Adaptation

When **Profile A** is selected:

- Beginner coding tips are displayed.
- Feedback is more detailed.
- Error messages include additional explanations.
- AI responses are longer and learning-oriented.
- Formatting feedback provides more guidance.
- The interface encourages the use of Explain, Fix, and Learn assistance.

### Experienced Developer Adaptation

When **Profile B** is selected:

- Beginner tips are hidden.
- Feedback becomes shorter.
- Error messages are concise.
- AI responses are more direct.
- Formatting assistance provides minimal feedback.
- Unnecessary beginner explanations are removed.

The purpose is to demonstrate that the system does not provide exactly the same assistance to every user.

---

## Features

### Code Editor

The prototype provides a simple code-entry area where users can enter sample programming code.

It is designed only to demonstrate adaptive coding assistance and is not intended to replace a complete IDE.

### Adaptive Feedback

The feedback area changes according to the selected user model.

For example, when a possible unmatched parenthesis is detected:

**Beginner:**

```text
Possible syntax issue detected.

The number of opening and closing parentheses does not match.
Check every '(' and make sure it has a corresponding ')'.
```

**Experienced:**

```text
Possible syntax issue: unmatched parentheses.
```

This demonstrates how the same issue can be presented differently depending on the user.

### Coding Hints

Coding hints are shown for the Beginner / Learner profile.

They are hidden for the Experienced Developer profile to reduce unnecessary guidance.

### Simulated AI Assistance

The prototype includes simulated AI assistance for:

- Generate
- Explain
- Fix
- Improve
- Learn
- Complete

The AI features are **simulated for prototype demonstration purposes**.

No external AI API or AI model is required.

The purpose of these features is to demonstrate how AI assistance could adapt according to the characteristics represented in the user model.

### Generate

Provides a sample code generation response.

Beginner users receive additional explanations about the generated code, while experienced users receive a shorter response.

### Explain

Demonstrates adaptive code explanation.

Beginner users receive longer and learning-oriented explanations.

Experienced users receive concise explanations.

### Fix

Provides simulated debugging suggestions.

The Beginner profile receives explanations about common programming mistakes, while the Experienced profile receives a shorter debugging checklist.

### Improve

Provides suggestions for improving code readability and structure.

The amount of explanation depends on the selected user profile.

### Learn

Provides learning-oriented programming assistance.

The Beginner profile receives step-by-step guidance, while the Experienced profile receives a short technical reference.

### Complete

Demonstrates simulated code completion.

Suggested code is accompanied by an explanation for beginner users, while experienced users receive only the essential completion.

### Basic Error Detection

The prototype performs simple demonstration-level checking, such as detecting unmatched parentheses.

This is not intended to function as a complete compiler, interpreter, or static code analyzer.

### Format Code

The **Format Code** button demonstrates basic formatting assistance by:

- Removing trailing spaces
- Reducing repeated blank lines
- Cleaning the entered code

The feedback after formatting also changes according to the user's formatting-assistance level.

### Dark / Light Mode

The interface includes a Dark Mode and Light Mode toggle for user comfort.

---

## User Model Representation

The user models are represented as JavaScript objects.

Example:

```javascript
const models = {

  beginner: {
    experience_level: "Beginner / Learner",
    years_coding: "0–5 years",
    languages: "Python, JavaScript",
    coding_frequency: "Occasional / Learning",
    auto_completion: "High",
    auto_formatting: "High",
    error_detection: "High",
    debugging_assistance: "High",
    ai_assistance: "High",
    guidance_level: "High"
  },

  experienced: {
    experience_level: "Experienced Professional",
    years_coding: "10+ years",
    languages: "Python, JavaScript, TypeScript, etc.",
    coding_frequency: "Daily",
    auto_completion: "Moderate",
    auto_formatting: "Low",
    error_detection: "Moderate",
    debugging_assistance: "High",
    ai_assistance: "High",
    guidance_level: "Low"
  }

};
```

These attributes are used by the prototype to determine how the interface and assistance should behave.

---

## Adaptation Rules

The prototype follows simple rule-based adaptation.

| User Characteristic | System Adaptation |
|---|---|
| High Guidance | Show beginner coding hints |
| Low Guidance | Hide beginner coding hints |
| Beginner Profile | Provide detailed feedback |
| Experienced Profile | Provide concise feedback |
| High Error Detection | Provide more descriptive error feedback |
| High Auto-formatting | Provide detailed formatting assistance |
| Low Auto-formatting | Provide basic formatting feedback |
| Beginner + AI Assistance | Provide teaching-style AI responses |
| Experienced + AI Assistance | Provide short and direct AI responses |

These rules demonstrate how information stored in a user model can influence system behavior.

---

## Technologies Used

The prototype uses:

- HTML5
- CSS3
- JavaScript

No framework, backend server, database, or external API is required.

---

## Project Structure

```text
adaptive-coding-system/
│
├── index.html
└── README.md
```

The complete prototype is contained inside a single HTML file.

---

## How to Run

1. Download or clone the project.
2. Open the project folder.
3. Locate `index.html`.
4. Open `index.html` using a modern web browser.

For example:

```text
Google Chrome
Microsoft Edge
Mozilla Firefox
Opera
```

No installation or server setup is required.

---

## How to Test the Adaptation

### Test 1 - Beginner / Learner

Select:

```text
Profile A - Beginner / Learner
```

Observe that:

- Beginner tips are visible.
- Feedback is detailed.
- The user model shows high guidance.
- Error feedback contains explanations.
- AI responses contain additional teaching information.

Enter sample code such as:

```python
def greet(name):
    return "Hello " + name

print(greet("World"))
```

Try the Generate, Explain, Fix, Improve, Learn, and Complete buttons.

---

### Test 2 - Experienced Developer

Select:

```text
Profile B - Experienced Developer
```

Observe that:

- Beginner tips disappear.
- Feedback becomes concise.
- The user model shows low guidance.
- Error feedback becomes shorter.
- AI responses become more direct.

Use the same code and AI actions used with Profile A.

The difference between the two responses demonstrates the adaptive behavior of the system.

---

## Example Error Test

Enter:

```python
print("Hello World"
```

The prototype detects that the opening and closing parentheses do not match.

For the Beginner profile, the system provides a detailed explanation.

For the Experienced profile, the system provides a short error message.

This demonstrates how the same coding situation results in different assistance depending on the active user model.

---

## Prototype Scope

This project is a **prototype of an adaptive coding environment**.

It is not intended to provide all features of professional development environments such as Visual Studio Code, PyCharm, NetBeans, or other IDEs.

The prototype focuses specifically on demonstrating:

1. User investigation
2. User modeling
3. User profiles
4. Adaptation rules
5. Adaptive system behavior

Features such as AI responses, debugging, formatting, and error detection are simplified or simulated where appropriate.

---

## Limitations

The prototype has several limitations:

- AI responses are simulated.
- It does not execute code.
- Error detection is limited to simple demonstration-level checks.
- Code completion is simulated.
- Auto-completion is represented in the user model but is not a full IDE-style completion engine.
- The user profiles simplify the diversity of real programmers.
- Only two user profiles are demonstrated.
- User characteristics are predefined rather than learned dynamically.
- The prototype does not automatically update a user's profile based on behavior.

These limitations are acceptable within the scope of demonstrating user modeling and adaptation.

---

## Possible Future Improvements

The prototype could later be extended with:

- Real syntax checking
- Actual code execution
- AI API integration
- Dynamic user modeling
- More user profiles
- Personalized code completion
- Programming language detection
- User preference settings
- Adaptive interface layouts
- Learning from user behavior
- Persistent user profiles

These features are outside the current prototype's required scope.

---

## Conclusion

The Adaptive Coding System Prototype demonstrates how a coding environment can change its assistance according to a user model.

Two user profiles are represented: a **Beginner / Learner** and an **Experienced Developer**.

The Beginner profile receives more detailed guidance, explanations, hints, and learning-oriented assistance. The Experienced profile receives fewer beginner prompts and more concise assistance.

The prototype demonstrates that information represented in a user model can be connected to specific adaptation rules and used to change the behavior of a coding-related system.

---

## Academic Purpose

This project was developed for educational purposes as part of the **CS412 User Modeling Laboratory Activity**.

The primary objective is to demonstrate the relationship between:

```text
User Investigation
        ↓
Data Analysis
        ↓
User Model
        ↓
Adaptation Rules
        ↓
Adaptive System Behavior
```

The project focuses on demonstrating clear user modeling and adaptation rather than building a complete professional IDE.
