# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
When I first ran the game, it opened in the browser through Streamlit and showed a simple interface where I could enter guesses and receive hints. The game appeared to work at first, but after playing a few times I noticed that some things were wrong.
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").
  First the hint weren't incorrect when the hidden is supposed to be lower it output higher in hint and when it supposed to be higher it output lower.The new game also doesn't work at all.

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
Claudecode
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
One correct suggestion from the AI was about the “New Game” button not working properly. The AI explained that when the game ended, the variable st.session_state.status was set to "won" or "lost". When the New Game button was clicked, the code reset the secret number and attempts but did not reset the status. Because of this, the program immediately stopped the new game since it still thought the game had already ended.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
Actually AI didn't get wrong anything.Since I specified what is kinda not working and actually checked before asking the AI

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
I decide when a bug is truly fix after rerunning the site manually ,and trying out wether the hint or range are supposed to be doing what they are showing.
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
  I run test for new game manually I first use the full allowed limit of guess ,and click on new game which allow me to keep guessing.I also check wether the number is the same by checking the hint when the same guess show different hint that mean that game sucessfully restarted.
- Did AI help you design or understand any tests? How?
AI didn't really hep me design or verified my test.
---

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
The secret number kept changing because Streamlit reruns the entire script every time the user interacts with the app, such as entering a guess or clicking a button. Each time the script reran, the code generated a new random number, which replaced the previous secret number.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
I would say when an Streamlit reruns it mean that the whole program runs again from top to bottom whenever something in the app changes. Session state is used to store values so they persist between these reruns. This allows important data, like the secret number or the score, to stay the same while the user continues interacting with the app.
- What change did you make that finally gave the game a stable secret number?
The one change that I maked that fixed the issue was adding a condition that checks if the secret number already exists in st.session_state. By using if "secret" not in st.session_state: before generating the random number, the program only creates the secret number once and keeps it stable for the rest of the game.
---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
  One habit I want to reuse in future labs or projects is testing the code and checking it carefully before assuming it works. This project showed me that even if AI suggests a fix, I should still run the program and verify that the result actually solves the problem.
- What is one thing you would do differently next time you work with AI on a coding task?
One thing I would do differently next time when working with AI on a coding task is use AI more actively to help analyze bugs and understand the logic of the code instead of trying to figure everything out on my own first.

- In one or two sentences, describe how this project changed the way you think about AI generated code.
This project changed the way I think about AI-generated code because it showed me that AI can be a helpful tool for debugging and understanding code, but its suggestions still need to be tested and verified before trusting them.