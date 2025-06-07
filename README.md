# Electronic Voting Machine (EVM) using ATmega32

This project implements an **Electronic Voting Machine** using the **ATmega32 microcontroller**, a **16x2 LCD display**, and a **4x3 matrix keypad**. It allows users to cast votes by entering a 2-digit candidate ID, view the list of candidates, check total results, and display the winner. It also includes an info section for version and credits.

## 🛠️ Features

- Vote casting using a unique 2-digit ID per candidate.
- LCD-based interactive menu:
  - List of candidates and their IDs
  - Voting process
  - Display of results
  - Winner announcement
  - Info/about section
- Simple keypress interface using 4x3 keypad
- Displays messages and confirmations after each step
- Handles invalid input and tie conditions

## 🔧 Hardware Components

- ATmega32 Microcontroller
- 16x2 LCD Display
- 4x3 Matrix Keypad
- Crystal Oscillator (typically 16 MHz or 1 MHz depending on fuse bits)
- 5V Power Supply
- Connecting wires and breadboard / PCB

## 🔌 Pin Configuration

| Component | ATmega32 Port |
|----------|----------------|
| LCD Data (D0-D7) | PORTA (PA0 - PA7) |
| LCD RS | PD6 |
| LCD RW | GND |
| LCD EN | PD5 |
| Keypad Rows | PB0 - PB3 |
| Keypad Columns | PB4 - PB6 |

> RW pin is grounded to make LCD write-only.

## 📲 Keypad Layout (4x3)
[1] [2] [3]
[4] [5] [6]
[7] [8] [9]
[*] [0] [#]

- `*` - Clear input
- `#` - Submit input
- `A` - Return to menu (use any unassigned key like `D` or custom)
- 
## 🚀 How to Use

1. On power-up, the system welcomes the user.
2. Main Menu is shown with 4 options:
   - `1` → View Candidate List
   - `2` → Cast a Vote
   - `3` → View Results
   - `4` → Info/About
3. To cast a vote:
   - Enter the 2-digit candidate ID (e.g., `1`, `6`)
   - Confirmation is shown
4. Results display total votes and per-candidate votes.
5. Option to display the winner (or tie if votes are equal).

## 👨‍💻 Software Tools

- Microchip Studio
- Proteus setup for testing

## 📁 File Structure

evm/
├── main.c # Main source code
├── README.md # Project documentation

## 🧠 Logic Summary

- Candidate IDs: `16`, `24`, `58`, `62`, `37`, `49`
- Votes are stored in array indexed to candidate position
- On vote submission:
  - ID is matched
  - Vote count is incremented
- Results and winner are dynamically displayed on LCD
- Input is debounced via wait loop after each keypress

## 🙋 Contributors

- Anirudh A Zalki  
- Harshad A Magdum  
- Shrivatsa Mandar  
- Naveen Rajdev  

Under guidance of: Ms.Umadevi 

## 📝 License

This project is free to use for academic and personal purposes.
