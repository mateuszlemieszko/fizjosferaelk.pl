# fizjosferaelk.pl

Strona internetowa fizjosferaelk.pl - statyczna strona HTML/CSS/JS gotowa do wdrożenia na Cloudflare Pages.

## Wdrożenie na Cloudflare Pages

### Opcja 1: Przez dashboard Cloudflare (Zalecana)

1. **Przygotuj repozytorium GitHub:**
   ```bash
   git add .
   git commit -m "Dodano konfigurację Cloudflare Pages"
   git push origin main
   ```

2. **Utwórz projekt w Cloudflare:**
   - Zaloguj się na [Cloudflare Dashboard](https://dash.cloudflare.com/)
   - Przejdź do sekcji "Pages"
   - Kliknij "Create a project"
   - Wybierz "Connect to Git"
   - Autoryzuj dostęp do GitHub i wybierz to repozytorium

3. **Konfiguracja projektu:**
   - **Project name:** `fizjosferaelk-pl`
   - **Production branch:** `main`
   - **Build command:** (pozostaw puste)
   - **Build output directory:** `/` (katalog główny)

4. **Dodaj domenę (opcjonalnie):**
   - Po wdrożeniu, w ustawieniach projektu przejdź do "Custom domains"
   - Dodaj domenę `fizjosferaelk.pl`
   - Skonfiguruj DNS zgodnie z instrukcjami

### Opcja 2: Przez CLI Wrangler

1. **Zainstaluj Wrangler:**
   ```bash
   npm install -g wrangler
   ```

2. **Zaloguj się do Cloudflare:**
   ```bash
   wrangler login
   ```

3. **Wdróż stronę:**
   ```bash
   wrangler pages publish . --project-name fizjosferaelk-pl
   ```

### Opcja 3: Przez npm script

```bash
npm run deploy
```

## Lokalne testowanie

Aby przetestować stronę lokalnie:

```bash
npm install
npm run serve
```

Strona będzie dostępna pod adresem `http://localhost:3000`

## Struktura projektu

```
fizjosferaelk.pl/
├── index.html          # Główna strona
├── contact.php         # Formularz kontaktowy
├── css/               # Style CSS
├── js/                # Skrypty JavaScript
├── img/               # Obrazy
├── fonts/             # Czcionki
├── _headers           # Konfiguracja nagłówków HTTP
├── _redirects         # Przekierowania
├── wrangler.toml      # Konfiguracja Cloudflare
└── package.json       # Zależności npm
```

## Funkcje

- ✅ Responsywna strona HTML/CSS/JS
- ✅ Konfiguracja Cloudflare Pages
- ✅ Optymalizacja wydajności (cache, gzip)
- ✅ Nagłówki bezpieczeństwa
- ✅ Gotowa do wdrożenia

## Uwagi

- Strona jest statyczna - `contact.php` nie będzie działać na Cloudflare Pages
- Dla formularza kontaktowego zalecam użycie:
  - Cloudflare Forms
  - Netlify Forms
  - Formspree
  - Lub przepisanie na Cloudflare Workers

## Pomoc

Jeśli napotykasz problemy:
1. Sprawdź logi wdrożenia w dashboard Cloudflare
2. Upewnij się, że repozytorium GitHub jest publiczne lub masz odpowiednie uprawnienia
3. Sprawdź konfigurację DNS dla domeny
