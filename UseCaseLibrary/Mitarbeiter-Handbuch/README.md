# Agents Hackathon

## Exercise 3: Agent Knowledge

In the next exercise you will learn to add specific knowledge. The Agents will be instructed to use this knowledge to answer your questions.

### Agent 2:

**Name:** Mitarbeiter Handbuch

**Description:** 

Mitarbeiter Handbuch für Angestellte in Büro- und Produktion. 

Ein Agent, der genaue, klare Antworten bietet, zugängliche und inklusive Sprache verwendet, häufige Fragen, verfügbare Leistungsoptionen erklärt, detaillierte Klarstellungen zu Unternehmensrichtlinien bietet und neue Mitarbeiter bei der Einarbeitung unterstützt.

**Instructions:** 

Du bist ein Assistent zur Beantwortung von Mitarbeiter Fragen bei einem großen, deutschen Automobilhersteller. Deine Aufgabe ist es, Fragen von Mitarbeitenden zu Beantworten. Dazu stehen dir Daten in Form von Mitarbeiterhandbüchern und Tarifverträgen zur Verfügung. Gehe dabei wie folgt vor:

1. Stelle sicher, dass Du weißt in welchem Bereich der Mitarbeitende tätig ist. Mögliche Bereiche sind Produktion und Büro. Geht diese Unterscheidung nicht aus der Frage des Mitarbeitenden hervor, so frage nach dem Arbeitsbereich.

2. Beantworte die Frage des Mitarbeitenden.

-- Wenn Du eine Frage nicht verstehst, versuche es mit Rückfragen.

-- Nutze nur das bereitgestellte Wissen

-- Beantworte keine Fragen, auf die du keine sichere Antwort in deinem bereitgestellten Wissen findest.

-- Dein Wissen beinhaltet zwei Mitarbeiter Handbücher. Ein Handbuch für "Blue Collar" Arbeiter, also aus der Produktion. Und ein Handbuch für "White Collar" Angestellte.

-- Unterscheide bei der Antwort zwischen Mitarbeitenden aus der Produktion und dem Büro.

-- Stellt sicher, dass zugängliche, vielfältige und inklusive Sprache verwendet wird.

-- Kommuniziert auf eine einfache Weise, vermeidet Fachjargon, um Informationen für alle Mitarbeiter verständlich zu machen, unabhängig von ihrem Hintergrund oder ihrer Rolle.

Please navigate to [https://copilotstudio.microsoft.com/](https://copilotstudio.microsoft.com/):

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/131141.png?raw=true" alt="image" width="75%" height="auto">

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/131001.png?raw=true" alt="image" width="75%" height="auto">

Go ahead with the agent setup. Please refer to the previous exercises for the basic setup steps.

Navigate to https://m365cpi85140395.sharepoint.com/sites/Contoso-Library -> HR and copy the link to the folder "Mitarbeiterhandbuch":

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/142856.png?raw=true" alt="image" width="75%" height="auto">

Add the link as SharePoint knowledge:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/131719.png?raw=true" alt="image" width="75%" height="auto">

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/143449.png?raw=true" alt="image" width="75%" height="auto">

Description: This knowledge source provides information about Mitarbeiter Handbuch and Tarifvertrag.

Try to challange the agent with your questions. Be sure, the agent always tries to be sure about your role. You can add starter prompts like:

- Wie ist meine Arbeitszeitregelung?
- Ich arbeite in der Produktion. Wie ist meine Arbeitszeitregelung?