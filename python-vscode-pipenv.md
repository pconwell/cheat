## Windows 10

### New Project

1. Open (empty?) folder in vs code (right click directory, open with vs code)
2. Terminal -> New Terminal
3. `$ pipenv install`
4. Close & Open project (per step #1)
5. Navigate to `.vscode` -> `settings.json` and note the path to the current pipenv
6. Edit the settings file to match:
```
{
   "python.venvPath": "C:/Users/[username]/.virtualenvs",
   "python.pythonPath": "C:/Users/[username]/.virtualenvs/[pipenv_path]/Scripts/python.exe"

   "code-runner.executorMap": {
       "python": "$pythonPath $fullFileName",
       }
   "code-runner.runInTerminal": true
}
```
7. Close & Open project (per step #1)
8. Terminal -> New Terminal
9. `$ pipenv install [package(s)]`
10. Right click -> `Run Code` (or `Run Python File in Terminal` depending on what extensions you have installed)
