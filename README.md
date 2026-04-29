# ⚡ POTWÓR VAULT v1.0

> **STATUS:** Live & Operational  
> **LIVE DEMO:** [KLIKNIJ TUTAJ, ABY OTWORZYĆ APLIKACJĘ](https://potwor-vault.vercel.app)

---

## 📖 O Projekcie
Nie musisz przeglądać kodu, aby zobaczyć jak działa system. Kliknij w powyższy link, zarejestruj się i przetestuj:
- Interaktywną bazę puszek Monster Energy.
- System oceniania (1-7 gwiazdek) z natychmiastową synchronizacją.
- Ranking generowany w czasie rzeczywistym na podstawie głosów społeczności.

## 🛠️ Specyfikacja Techniczna

Projekt został zaprojektowany w architekturze **Full-Stack Serverless**, co zapewnia wysoką skalowalność przy minimalnych kosztach utrzymania.

### 💻 Frontend (Client Side)
* **Framework:** [React 18](https://reactjs.org/) (Functional Components + Hooks)
* **Build Tool:** [Vite](https://vitejs.dev/) – zapewnia błyskawiczne przeładowanie (HMR) i zoptymalizowany bundle produkcyjny.
* **State Management:** Wykorzystanie natywnego `useState` oraz `useEffect` do synchronizacji danych z bazą w czasie rzeczywistym.
* **Stylizacja:** Pure CSS z wykorzystaniem zmiennych (CSS Variables) dla łatwej implementacji trybu Dark Mode i spójnej kolorystyki marki Monster.
* **Komunikacja:** Asynchroniczne zapytania do API przy użyciu biblioteki `@supabase/supabase-js`.

### 🗄️ Backend & Database (BaaS)
* **Silnik Bazy Danych:** [PostgreSQL](https://www.postgresql.org/) hostowany na platformie Supabase.
* **Autentykacja:** Supabase Auth (GoTrue) – obsługa sesji, bezpieczne przechowywanie haseł (hashowanie) oraz system potwierdzeń e-mail.
* **Bezpieczeństwo (RLS):** Zaimplementowano polityki **Row Level Security**, które gwarantują, że:
    * Użytkownicy anonimowi mają dostęp tylko do odczytu danych publicznych.
    * Użytkownicy zalogowani mogą modyfikować wyłącznie własne rekordy w tabelach `ratings` i `user_progress`.
* **Logika Bazy:** Wykorzystanie unikalnych kluczy kompozytowych (`monster_id` + `user_id`), aby zapobiec duplikowaniu ocen.

### 🌐 Infrastruktura (DevOps)
* **Hosting:** [Vercel](https://vercel.com/) – automatyczny CI/CD (Continuous Integration / Continuous Deployment). Każdy "push" na gałąź `main` skutkuje natychmiastową aktualizacją wersji produkcyjnej.
* **E-mail Service:** Zintegrowany system powiadomień SMTP do obsługi weryfikacji kont i resetowania haseł.

## 🛠️ Status Projektu & Aktualizacje

Aplikacja jest w fazie **Active Development**. Stale monitorujemy bazę danych i wprowadzamy poprawki zgłaszane przez społeczność.

### 🔄 Ostatnie zmiany (v1.0-STABLE):
- **[FIX]** Naprawiono błąd synchronizacji rankingu – teraz średnia ocen aktualizuje się natychmiast po zmianie.
- **[DESIGN]** Dodano "fancy" szablon maila aktywacyjnego w klimacie Vault.
- **[DB]** Zoptymalizowano zapytania SQL dla lepszej wydajności przy dużej liczbie rekordów.

### 🚧 Planowane funkcje (Roadmap):
- [ ] System komentarzy pod każdym smakiem Monstera.
- [ ] Powiadomienia o nowych limitowanych edycjach w sklepach.
- [ ] Tryb offline (PWA).
- [ ] Aplikacja mobilna (Android)

---

## 🛡️ Bezpieczeństwo i Dane
Projekt wykorzystuje **Row Level Security (RLS)** w bazie Supabase. Oznacza to, że:
1. Twoje hasło jest szyfrowane i niewidoczne nawet dla administratora.
2. Możesz edytować i usuwać tylko swoje własne oceny.
3. System weryfikacji e-mail zapobiega spamowaniu rankingu przez boty.
