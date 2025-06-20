# Agents Hackathon

## Exercise 2: Agent Knowledge

In the next exercise you will learn to add specific knowledge. The Agents will be instructed to use this knowledge to answer your questions.

### Agent 1:

This Agent will be configured using the M365 Copilot Agent Builder. Please refer to the previous exercises for the basic setup steps.

**Name:** Umsatzsteuer-Assistent

**Description:** 

Dieser Assistent hilft bei Fragen und Problemen rund um die deutsche Umsatzsteuer.

**Instructions:** 

Du bist ein Assistent in der Finanzabteilung eines deutschen Unternehmens und hilfst bei Fragen und Problemen rund um die deutsche Umsatzsteuer.

-- verstehe die Frage des Benutzers. Wenn Du dir nicht sicher bist, ob du sie verstanden hast, dann frage nach.

-- Sei stets genau und präzise. Bei diesen Themen können schon kleine Abweichungen der Formulierung zu falschen Ergebnissen führen

-- Sei stets freundlich und nutze einen informellen Ton

-- Biete neben einer ausführlichen Antwort mit entsprechendem Fachjargon auch eine kurze Zusammenfassung in einfacher Sprache an

Navigate to [https://www.microsoft365.com/chat](https://www.microsoft365.com/chat).

Create a new agent

<img src="https://github.com/AndreasExner/AgentsHackathon/UseCaseLibrary/Umsatzsteuer-Assistent(web)/113154.png?raw=true" alt="image" width="75%" height="auto">

Add https://usth.bundesfinanzministerium.de/usth/2023 as knowledge:

<img src="https://github.com/AndreasExner/AgentsHackathon/UseCaseLibrary/Umsatzsteuer-Assistent(web)/113446.png?raw=true" alt="image" width="75%" height="auto">

Optional: add starter prompts

Again, the instructions are very rudimentary. Feel free to optimize them.