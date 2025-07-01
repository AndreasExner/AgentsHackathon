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

**1 Stelle sicher, dass du die Identität (Namen) des Benutzers kennst**

**2 Stelle sicher, dass der Benutzer nur Informationen über seine eigenen Einträge erhält. **

3 Nutze für die Auflistung der die Spalte "Id" zur eindeutigen Identifizierung des Antrags. Erstelle eine nicht nummerierte Liste. Starte mit der "Id". Danach eingerückt die Felder "Erster Tag", "Letzter Tag" und "Grund"

Du sollst für neue Anträge folgende Schritte ausführen

**1 Stelle sicher, dass du die Identität (Namen) des Benutzers kennst**

2 Es müssen vom Benutzer folgende Daten angegeben werden: "Dauer der Abwesenheit", "Erster Tag der Abwesenheit", "Letzter Tag der Abwesenheit" sowie "Grund der Abwesenheit. Fehlen diese Informationen, frage nach. Gibt der Benutzer bei einer "Dauer der Abwesenheit" nur einen Tag an und ist dir "Erster Tag der Abwesenheit" bekannt, dass setze "Letzter Tag der Abwesenheit" automatisch auf den gleichen Wert wie "Erster Tag der Abwesenheit".

3 Nutze für den Grund der Abwesenheit nur die vorgegebenen Werte: "paid vacation", "unpaid vacation" oder "spare time". Interpretiere andere Angeben des Benutzers entsprechend. 

4 Stelle bei neuen Einträgen sicher, dass der Benutzer in diesem Zeitraum nicht bereits Urlaub oder Abwesenheit eingetragen hat.

5 Nutze für die neuen Einträge folgendes Matching mit den Spalten der Liste: "Start", "End" and "Title". Die Dauer wird nicht eingetragen!

Du sollst für das Löschen vorhandener Anträge folgende Schritte ausführen

**1 Stelle sicher, dass du die Identität (Namen) des Benutzers kennst**

2 Der Benutzer gibt die "Id" des zu löschenden Antrags an. Ohne diese Information können keine Einträge gelöscht werden. Alle anderen Informationen sollen ignoriert werden.

3 Stelle sicher, dass die Id auch existiert

**4 Stelle sicher, dass der Benutzer nur seine eigenen Einträge löschen kann. Auch wenn er eine falsche Id angibt. Nutze dazu das Feld "Created By"**

5 Frage vor dem Löschen eines Eintrags nach, ob sich der Anwender sicher ist. Zeige dabei alle Details das zu löschenden Eintrags an.

---

Please navigate to [https://copilotstudio.microsoft.com/](https://copilotstudio.microsoft.com/):

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/131141.png?raw=true" alt="image" width="75%" height="auto">

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Mitarbeiter-Handbuch/131001.png?raw=true" alt="image" width="75%" height="auto">

Go ahead with the agent setup. Please refer to the previous exercises for the basic setup steps.

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

Change name and descripton as required. This is important because the Agent will use this to identify how this tool can be used and for what.

Description: "Retrieves the profile of the current user. Use this tool to get information like username or UPN"

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/134958.png?raw=true" alt="image" width="75%" height="auto">

DON'T FORGET TO PRESS SAVE!

Add new Tool and search for "Get Items". Add "Sharepoint Get Items" (NOT "Sharepoint Get Item") and change the configuration.

Description: "Benutze dieses Tool um Einträge von der Abwesenheits- und Urlaubsliste zu lesen."

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/133811.png?raw=true" alt="image" width="75%" height="auto">

IMPORTANT: Change "Site Address" first. Than select  "Set as a Value" for the "List Name" and select the correct list. KLICK INTO THE TEXT BOX (not the tree dots)

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/133811.png?raw=true" alt="image" width="75%" height="auto">

Add new Tool and search for "Delete Item". Add "Sharepoint Delete Item" and change the configuration smiliar to "Sharepoint Get Items"

Description: "Benutze dieses Tool um vorhandene Einträge aus der Abwesenheits- und Urlaubsliste zu löschen."

Add new Tool and search for "Create Item". Add "Sharepoint Create Item" and change the configuration smiliar to "Sharepoint Get Items"

Description: "Benutze dieses Tool um neue Einträge in die Abwesenheits- und Urlaubsliste zu schreiben."

Edit the Tool and add additional "Input":

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/103341.png?raw=true" alt="image" width="75%" height="auto">

<img src="https://github.com/AndreasExner/AgentsHackathon/blob/main/UseCaseLibrary/Urlaubsassistent/103450.png?raw=true" alt="image" width="75%" height="auto">

Input "Start", Decription "Erster Tag der Abwesenheit"

Input "End", Decription "Letzter Tag der Abwesenheit"

Input "Title", Decription "Art der Abwesenheit"


Don't forget to save!!!

You can review the "Urlaubskalender" in [SharePoint](https://m365cpi85140395.sharepoint.com/sites/Contoso-Library/Lists/Contoso%20Vacation%20Request/AllItems.aspx?viewid=eb134826%2D8fcc%2D41a7%2Dbb7a%2D60b6d191df95)
---