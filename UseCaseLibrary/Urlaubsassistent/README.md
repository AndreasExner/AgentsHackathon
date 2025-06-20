# Agents Hackathon

## Exercise 4: Agent Tools (Actions)

In the next exercise you will learn to add tool (actions) to an agent. The Agents will be instructed to use this tools to perform actions in other systems.

### Agent 1:
---
**Name:** Urlaubsassistent

**Description:**

Assistent für Urlaubsanträge / Abwesenheit

Dieser Assistent hilft bei der Erstellung von Anträgen für Urlaub und Abwesenheit. Die Daten werden automatisch in einen zentralen Kalender geschrieben. Der Antragssteller kann zudem jederzeit nach geplanten Urlauben Fragen oder Einträge löschen.

**Instructions:** 

Du bist ein Assistent, welcher bei der Verwaltung von Urlaubsanträgen und Abwesenheit hilft. Für diesen Zweck kannst Du auf eine Liste mit bereits gestellten Anträgen zugreifen. In diese Liste trägst Du auch neue Anträge ein. Auf Wunsch kannst Du auch bestehende Einträge löschen.

Du sollst für das Anzeigen der vorhandenen Anträge folgende Schritte ausführen:

**1 Ermittle die Benutzer Identität**

**2 Stelle sicher, dass der Benutzer nur Informationen über seine eigenen Einträge erhält. Nutze dazu das Feld "Created by"**

3 Nutze für die Auflistung der die Spalte "Id" zur eindeutigen Identifizierung des Antrags. Erstelle eine nicht nummerierte Liste. Starte mit der "Id". Danach eingerückt die Felder "Erster Tag", "Letzter Tag", "Dauer" und "Grund"

Du sollst für neue Anträge folgende Schritte ausführen

**1 Ermittle die Benutzer Identität**

2 Es müssen vom Benutzer folgende Daten angegeben werden: "Dauer der Abwesenheit", "Erster Tag des Abwesenheit", "Letzter Tag des Abwesenheit" sowie "Grund der Abwesenheit. Nutze dazu das Tool Neuer Abwesenheitsantrag"

3 Stelle bei neuen Einträgen sicher, dass der Benutzer in diesem Zeitraum nicht bereits Urlaub oder Abwesenheit eingetragen hat.

4 Nutze für die neuen Einträge folgendes Matching mit den Spalten der Liste: "Start"={Global.FirstAbsenceDay}, "End"={Global.LastAbsenceDay}, "Title"={Global.AbsenceType}. Die Dauer wird nicht eingetragen!

Du sollst für für das Löschen vorhandener Anträge folgende Schritte ausführen

1 Der Benutzer gibt die "Id" des zu löschenden Antrags an. Alle andere Informationen sollen irgnoriert werden.

2 Stelle sicher, dass die Id auch existiert

**3 Ermittle die Benutzer Identität**

**4 Stelle sicher, dass der Benutzer seine eigenen Einträge löschen kann. Auch wenn er eine falsche Id angibt. Nutze dazu das Feld "Requestor"**

5 Frage vor dem Löschen eines Eintrags nach, ob sich der Anwender sicher ist. Zeige dabei alle Details das zu löschenden Eintrag an.

---

Please navigate to [https://copilotstudio.microsoft.com/](https://copilotstudio.microsoft.com/):

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/141200.png?raw=true" alt="image" width="75%" height="auto">

Go ahead with the agent setup. Please refer to the previous exercises for the basic setup steps.

In preparation for the next steps, we have to change some setting for the agent.

Open "Settings":

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/092844.png?raw=true" alt="image" width="75%" height="auto">

Change the agent behavior:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/093134.png?raw=true" alt="image" width="75%" height="auto">

Ensure, that the Agent only use the provided knowledge:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/093339.png?raw=true" alt="image" width="75%" height="auto">

---

We need a "Topic" to guide the user through the question about new requests.

**Topics:**

**Name:** Neuer Abwesenheitsantrag

**Prompt:**

Frage die notwendigen Daten für einen neuen Abwesenheitsantrag ab. Die nötigen Informationen sind: "Art der Abwesenheit (Paid Vacation, Spare Time, Unpaid Vacation)", "Dauer der Abwesenheit (Tage)", "Erster Tag der Abwesenheit (Datum)" und nur wenn die Dauer größer ist als 1 Tag: "Letzter Tag der Abwesenheit (Datum)"

Create a new topic:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/092412.png?raw=true" alt="image" width="75%" height="auto">

After creating the topic, the variables must be set to "global". We need them later:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/091547.png?raw=true" alt="image" width="75%" height="auto">

---

**Tools (Actions**)

Now we come to the tools (actions). With these tools, we enable the agent to communicate with other systems and perform tasks for us.

IMPORTANT: A tool will require a connection. The connection must be enabled once for each tool during the initial setup. This is NOT the same connection used during test or execution. You will be asked again (once) during the first test / execution to esteblish the connection. 

Add a new tool:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/094022.png?raw=true" alt="image" width="75%" height="auto">

Search for "Get My Profile":

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/094340.png?raw=true" alt="image" width="75%" height="auto">

Select an existing connection or create a new one. Go ahead with "add and configure":

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/094555.png?raw=true" alt="image" width="75%" height="auto">

Change name and descripton as required. This is important because the Agent will use this to identify how this tool can be used and for what:

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/095059.png?raw=true" alt="image" width="75%" height="auto">

Add new Tool and search for "Get Items". Add "Sharepoint Get Items" (NOT "Sharepoint Get Item") and change the configuration.

IMPORTANT: Change "Site Address" first. Than select  "Custom Value" for the "List Name" and select the correct list. KLICK INTO THE TEXT BOX. The drop-down arrow is currentyl not working (looks like a bug)

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/100302.png?raw=true" alt="image" width="75%" height="auto">

Add new Tool and search for "Create Item". Add "Sharepoint Create Item" and change the configuration smiliar to "Sharepoint Get Items"

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/100646.png?raw=true" alt="image" width="75%" height="auto">

Add new Tool and search for "Delete Item". Add "Sharepoint Delete Item" and change the configuration smiliar to "Sharepoint Get Items"

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/101210.png?raw=true" alt="image" width="75%" height="auto">

You can review the "Urlaubskalender" in [SharePoint](https://m365cpi85140395.sharepoint.com/sites/Contoso-Library/Lists/Contoso%20Vacation%20Request/AllItems.aspx?viewid=eb134826%2D8fcc%2D41a7%2Dbb7a%2D60b6d191df95)
---