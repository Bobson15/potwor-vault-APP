# ⚡ POTWÓR VAULT v1.0

> **STATUS:** Live & Operational  
> **LIVE DEMO:** [KLIKNIJ TUTAJ, ABY OTWORZYĆ APLIKACJĘ](https://potwor-vault.vercel.app)

---

## 📖 O Projekcie
Nie musisz przeglądać kodu, aby zobaczyć jak działa system. Kliknij w powyższy link, zarejestruj się i przetestuj:
- Interaktywną bazę puszek Monster Energy.
- System oceniania (1-7 gwiazdek) z natychmiastową synchronizacją.
- Ranking generowany w czasie rzeczywistym na podstawie głosów społeczności.

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
