# Social Engineering Training Game  
**Version 1.0**  

### Prepared by  
Frederic Stresau, Simon Chummar, Alexander C. Bodoh, Quy Pham, Jackson Harper  
**Florida Polytechnic University SSE Group 7**  
**Date:** 4/24/2024  

---

## Abstract  
The goal of this project is to design and develop a game (software) to evaluate users' awareness about social engineering attacks in an entertaining format. It is a simple mobile game application that:  
- Asks users questions about different types of social engineering attacks and basic protection techniques.  
- Provides feedback on user answers and displays correct answers.  
- Allows users to create separate accounts, protecting their data through encryption.  
- Includes a profile page to show users their improvement over time.  

---

## Core Design  

### 1. System Architecture  
The application uses a **repository system architectural style**, where main game components interact with a central repository (encrypted JSON files).  
Key aspects include:  
- Data storage in **encrypted JSON files** for past scores, usernames, passwords, and questions.  
- Passwords hashed using **SHA-256** and files encrypted with **MD5** and **DES**.  
- Development in **Android Studio** with **Java**, using the libraries **Moshi** (JSON handling) and **Jasypt** (encryption).  
- Testing and debugging supported by Android Studio's device emulators.

### 2. System Features  
#### Core Features:  
- **Account Creation:** Users can create accounts with a secure password.  
- **Log-in System:** Existing users log in with their username and password.  
- **Strong Password Enforcement:** Ensures passwords are at least 12 characters long, include uppercase, lowercase, numbers, and special characters.  
- **SHA-256 Password Hashing:** Prevents attackers from learning plaintext passwords.  
- **Data Encryption:** User score history is encrypted with MD5 and DES, using the SHA-256 salted password hash as the encryption key.  
- **Quiz Gameplay:** A five-question quiz with multiple-choice answers randomly selected from a pool of 36 questions.  
- **Feedback System:** Provides feedback on correct answers for each question.  
- **Profile Page:** Displays past scores in reverse chronological order to track user progress.  

---

## Source Code  
The source code for this project is available on GitHub:  
[alexander-c-b/secure-software-engineering](https://github.com/alexander-c-b/secure-software-engineering)

---

## Video Demo  
A video demo of the project can be found here:  
[Team 7 Final Project Demo Video](https://drive.google.com/file/d/1x2DemoVideoURLHere)

---

## Testing Results  

### Unit Test Results  
- **Encryptor:**  
  ✓ Encrypts and decrypts files using salted hashes.  
  ✓ Ensures unique file hash and encryption key.  

- **JsonEncoder:**  
  ✓ Loads, encrypts, and decrypts JSON data.  

- **Authenticator:**  
  ✓ Enforces username and password requirements.  
  ✓ Validates successful account creation and logins.  

- **Game Components:**  
  ✓ Randomizes quiz questions without repetition.  
  ✓ Provides correct feedback and tracks score.  

- **UI Elements:**  
  ✓ Displays all necessary game features (e.g., questions, profile page).  

### Integration Testing Results  
- Accounts create encrypted score files.  
- Successfully logs in and provides access to the game and profile.  
- Quiz gameplay uses on-device question data and saves scores to the profile.  

### System Testing  
- **Performance Testing:** All functions respond within 2 seconds.  
- **Functional Testing:** Full end-to-end use case functionality (account creation, login, game, profile view, logout).  
- **Security Testing:** Unauthorized access to user data was successfully blocked.  

---

## Conclusions  
The Social Engineering Training Game provides an engaging and educational platform for users to learn about social engineering attacks. The app securely handles user data while offering intuitive features for tracking progress and improving awareness. Our simple, maintainable architecture and reliance on high-quality libraries ensured a reliable and secure application.  
