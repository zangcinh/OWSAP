**1.Pre-Generated Questions:**
- Common questions may have answers known to family, friends, or public sources, making them vulnerable.
- Examples include: “What is your mother’s maiden name?” or “What is your favorite color?”

**2.Self-Generated Questions:**

- Users may create insecure questions, bypassing the security mechanism.
- Examples of weak questions: “What is 1+1?” or “My password is S3cur1ty!”

**3.Test Objectives:**

- Evaluate the complexity and effectiveness of both pre-generated and self-generated security questions.
- Assess the feasibility of brute-forcing or discovering answers.

**4.Testing Methods:**

- Pre-Generated Questions: Identify weak questions by examining a list obtained during account creation or password recovery processes.
- Self-Generated Questions: Create or modify questions to test for weak setups, focusing on questions that could be easily exploited.
- Brute-Force Testing: Check if multiple incorrect answers trigger a lockout mechanism. Evaluate the strength of questions based on how easily answers can be discovered or guessed.

**5.Additional Considerations:**

- Assess the number of questions required and the strength of each question.
- Determine if the system allows unlimited attempts or if there are lockout periods.
