# AAShell - Shell Personalizat în C

## 📖 Descriere
AAShell este un mini-shell interactiv, dezvoltat în **C**, care oferă o experiență personalizată de gestionare a comenzilor Linux. Acest shell imită funcționalitățile unui shell standard, oferind suport pentru execuția comenzilor de sistem, gestionarea proceselor în fundal, utilizarea **pipe-urilor**, **operatorilor logici (`&&`, `||`)**, **redirecționarea intrării/ieșirii** și **un istoric al comenzilor**.

### 🔹 **Principalele componente**
#### Structuri și variabile globale
- `BackgroundProcess`: Structură pentru a stoca procesele din fundal.
- `background_processes` și `background_count`: Listează procesele din fundal și numărul acestora.
- `history` și `history_count`: Istoricul comenzilor utilizatorului.
- `current_pid` și `suspended_pid`: PID-ul procesului curent și al celui suspendat.

#### Interfață și mesaje interactive
- `print_prompt`: Afișează prompt-ul shell-ului într-un format personalizat.
- `welcome_message`: Mesaj de bun venit pentru utilizatori.

---

### 🚀 **Funcționalități principale**
#### 📌 Istoricul comenzilor
- `add_to_history`: Adaugă comenzi în istoric pentru referințe viitoare.
- `print_history`: Afișează istoricul comenzilor utilizatorului.

#### 📌 Execuția comenzilor
- `execute_command`: Rulează comenzi simple introduse de utilizator.
- `execute_pipe`: Permite execuția a două comenzi folosind **pipe-uri** (`|`).
- `execute_redirection`: Gestionează **redirecționarea intrării/ieșirii** (`<`, `>`).
- `execute_with_status`: Rulează comenzi și interpretează **codul de execuție**.
- `execute_logical_commands`: Permite execuția comenzilor cu **operatori logici (`&&`, `||`)**.

#### 📌 Gestionarea proceselor în fundal
- `print_jobs`: Listează procesele care rulează în fundal.
- `bring_to_foreground`: Aduce un proces din fundal în prim-plan.
- `kill_background_process`: Omoară un proces care rulează în fundal.

#### 📌 Suspendare și reluare procese
- `signal_handler`: Gestionează semnalul `SIGTSTP` (`Ctrl+Z`) pentru a suspenda un proces activ.
- `handle_fg_command`: Reia procesele suspendate și le aduce în prim-plan.

---

### ⚙️ **Gestionarea semnalelor și controlul execuției**
- **Suspendarea proceselor (`SIGTSTP`)**: Când utilizatorul apasă `Ctrl+Z`, procesul curent este suspendat și poate fi reluat ulterior.
- **Reluarea proceselor (`SIGCONT`)**: Procesul suspendat poate fi readus în execuție folosind `fg`.

---

## 🔧 Cum se compilează și rulează
1. **Compilează proiectul:**
   ```sh
   gcc shell_so.c -o aashell
   ```
2. **Rulează shell-ul personalizat:**
   ```sh
   ./aashell
   ```
3. **Pentru a ieși:**
   ```sh
   exit
   ```
