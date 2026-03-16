# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [The purpose of the game is to let the player guess a secret number within a selected range while receiving hints about whether the guess is too high or too low. ] Describe the game's purpose.
- [ I found that the hints were backwards, the secret number changed because of Streamlit reruns, and the New Game button did not properly reset the game state.] Detail which bugs you found.
- [ I fixed the hint logic so the messages matched the guesses correctly. I made the secret number stable by storing it in st.session_state and only creating it once with a guard condition. I also fixed the New Game button by resetting the game status so a new round could start normally. In addition, I moved game logic into logic_utils.py to separate the logic from the Streamlit UI.] Explain what fixes you applied.

## 📸 Demo

- [game_demo.png ] [Insert a screenshot of your fixed, winning game here]

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, insert a screenshot of your Enhanced Game UI here]
