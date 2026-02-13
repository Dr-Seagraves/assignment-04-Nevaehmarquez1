# AI Audit Appendix (Assignment 04)

## Tool(s) Used
- GitHub Copilot

## Task(s) Where AI Was Used
- I asked it to run the regressions and make the scatter plots for me. It also helped me with the coefficient comparison, the slope interpretation, and the R2 in the report

## Prompt(s)
1. "Given the existing data and the data I imported could you estimate three simple OLS regressions of REIT annual returns on different predictors? The three are: ret (annual) ~ div12m_me (dividend yield), ret (annual) ~ prime_rate (prime loan rate), ret (annual) ~ ffo_at_reit (FFO to assets — fundamental performance)"
2. "In my report, I need help with the coefficient comparison and slope interpretation parts. Could you explain to me what those are and what numbers to put?"
3. "Tell me what the R2 means for this assignment/report"

## Output Summary
1. It generated the OLS regressions and made the scatter plots for me.
2. The AI looked at the slope for each predictor of div12m_me, prime_rate, and ffo_at_reit. It compared which slope was largest and which was smallest. This helped show which variable has the strongest relationship with ret. Then, the AI used the slope from each regression to explain how much ret changes when the predictor increases by 1 unit. If the variable was measured in percent, it described the change as a 1 percentage point increase. Lastly, it plugged the numbers in for me so I knew what to talk about.
3. It said the "R2 values from the three models are: ret ~ div12m_me: 0.002, ret ~ prime_rate: 0.016, ret ~ ffo_at_reit: 0.000" and "In this report, R2 is the percent of variation in annual REIT returns that the single predictor explains, and here it is very small" and "They were very weak (near zero), which means each model has low explanatory power and the predictor alone does not explain much of the variation in returns"

## Verification & Modifications (Disclose • Verify • Critique)
- **Verify:** I ran the regression code myself and checked that the coefficient estimates and R2 values matched what Copilot produced. I also compared the regression tables and made sure the scatter plots aligned with the direction of the slopes. 
- **Critique:** The AI wasn’t explaining things very clearly at first. It mostly gave me the numbers without breaking them down in a simple way, so I had to ask it to explain the coefficient comparison and slope interpretation more clearly so I could actually understand what they meant. After that, it helped define how weak the R2 values were and what that meant for model strength.
- **Modify:** I had to slow down and really think through what the numbers meant because at first I wasn't fully understanding it. I rewrote the explanations in simpler language so I could actually explain them myself if asked. I also added a sentence explaining that the R2 values are really small, so these predictors don’t explain much, because that part wasn’t obvious to me at first. I simplified everything so it made sense to me, not just to the computer.

## If No AI Tools Used

