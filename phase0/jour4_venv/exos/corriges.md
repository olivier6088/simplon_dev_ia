# Corrigés — Environnements virtuels Python (venv)

Les solutions proposent des **commandes prêtes à l’emploi** pour macOS/Linux (Bash) et Windows
(**PowerShell** et **CMD**). Adaptez `python` ↔ `python3` selon votre installation.

> **Astuce** : dans PowerShell, exécuter des scripts peut être restreint. Si besoin (session admin) :  
> `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`

---

## Exercice 1 — Créer un venv

**macOS/Linux (Bash)**
```bash
mkdir -p mon_projet_venv
cd mon_projet_venv
python -m venv .venv
ls -la .venv
```

**Windows PowerShell**
```powershell
mkdir mon_projet_venv
Set-Location mon_projet_venv
python -m venv .venv
Get-ChildItem .venv
```

**Windows CMD**
```cmd
mkdir mon_projet_venv
cd mon_projet_venv
python -m venv .venv
dir .venv
```

**Vérification du chemin absolu du Python du venv**
- macOS/Linux : `readlink -f .venv/bin/python` (ou `python -c "import sys; print(sys.executable)"` après activation)
- Windows : `Resolve-Path .venv\Scripts\python.exe` (PowerShell) ou chemin affiché par `where python` après activation

---

## Exercice 2 — Activer et vérifier l’isolement

**Activer**
- macOS/Linux (Bash) : `source .venv/bin/activate`
- Windows PowerShell : `.\.venv\Scripts\Activate.ps1`
- Windows CMD : `.\.venv\Scripts\activate.bat`

**Contrôles**
```bash
python -m pip --version
python - <<'PY'
import sys; print(sys.executable)
PY
```
PowerShell : `python -m pip --version` puis `python -c "import sys; print(sys.executable)"`  
CMD : idem.

**Liste minimale des paquets**
```bash
python -m pip list
```

---

## Exercice 3 — Installer une version précise (ex. requests 2.31.0)

**Tous OS**
```bash
python -m pip install --upgrade pip
python -m pip install requests==2.31.0
python - <<'PY'
import requests; print(requests.__version__)
PY
```

PowerShell : `python -c "import requests; print(requests.__version__)"`  
CMD : `python -c "import requests; print(requests.__version__)"`

---

## Exercice 4 — Figer l’environnement (requirements.txt)

```bash
python -m pip freeze > requirements.txt
head -n 30 requirements.txt || sed -n '1,30p' requirements.txt
```

Windows (PowerShell/CMD) : `type requirements.txt`

---

## Exercice 5 — Recréer l’environnement à l’identique

**Supprimer l’ancien venv**
- macOS/Linux : `deactivate` (si actif) puis `rm -rf .venv`
- Windows PowerShell : `deactivate` puis `Remove-Item -Recurse -Force .venv`
- Windows CMD : `deactivate` puis `rmdir /s /q .venv`

**Recréer et restaurer**
```bash
python -m venv .venv
# activez le venv selon votre OS, puis :
python -m pip install -r requirements.txt
python -m pip list
```

---

## Exercice 6 — Contraintes de versions & mise à jour

```bash
python -m pip install "urllib3>=2,<2.2"
python - <<'PY'
import urllib3; print(urllib3.__version__)
PY
python -m pip install --upgrade "urllib3>=2,<2.2"
python - <<'PY'
import importlib, urllib3; importlib.reload(urllib3); print(urllib3.__version__)
PY
```

PowerShell/CMD : remplacez les blocs `python - <<'PY' ... PY` par des commandes `python -c "..."`.

---

## Exercice 7 — Désinstaller et vérifier

```bash
python -m pip uninstall -y urllib3
python - <<'PY'
try:
    import urllib3
    print("Toujours présent:", urllib3.__version__)
except Exception as e:
    print("Échec attendu:", e)
PY
```
L’erreur attendue est **ModuleNotFoundError**.

---

## Exercice 8 (bonus) — Variable d’environnement

**macOS/Linux**
```bash
export APP_ENV=dev
python -c "import os; print(os.getenv('APP_ENV'))"
```

**Windows PowerShell**
```powershell
$Env:APP_ENV = "dev"
python -c "import os; print(os.getenv('APP_ENV'))"
```

> Persistance : ajoutez ces lignes à votre profil de shell (`~/.bashrc`, `~/.zshrc`, `$PROFILE` PowerShell, etc.).

---

## Exercice 9 (bonus) — venv comme noyau Jupyter

```bash
python -m pip install ipykernel
python -m ipykernel install --user --name venv-cours --display-name "Python (venv-cours)"
jupyter kernelspec list
```

---

## Exercice 10 (bonus) — `.gitignore` minimal

Créez un fichier `.gitignore` contenant au minimum :
```gitignore
.venv/
__pycache__/
*.pyc
build/
dist/
*.egg-info/
```

**Vérifier** : `git status` ne doit plus afficher ces éléments.

---

## Foire aux problèmes (FAQ)
- **“ls n’est pas reconnu”** → vous êtes sous Windows : utilisez `dir`.
- **Scripts bloqués sous PowerShell** → exécuter (profil utilisateur) : `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`.
- **`python` lance l’ancienne version** → vérifiez l’activation du venv et `where python` (Windows) / `which -a python` (Unix).
- **Conflits de dépendances** → recréez le venv puis installez avec des versions épinglées, ou réduisez la plage autorisée.
