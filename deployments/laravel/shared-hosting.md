
# SSH Deployment Guide (Laravel Project)

## 1. Connect to Server via SSH

```bash
ssh user@your-server-ip
```

---

## 2. Navigate to Domains Directory

List all files/directories in the root:

```bash
ls -la
```

Move into the `domains` directory:

```bash
cd domains
ls -la
```

Enter the specific domain you want to work on:

```bash
cd your-domain.com
ls -la
```

---

## 3. Navigate to `public_html`

```bash
cd public_html
```

⚠️ **Warning:**
The next step will permanently delete everything in this directory. Double-check you’re in the correct location.

Go back to the domain root:

```bash
cd ..
```

Delete all existing files (including `public_html`):

```bash
rm -rf *
```

---

## 4. Clone the Repository

```bash
git clone <repository-url>
```

Move into the project directory (if the repo created one):

```bash
cd project-folder
```

---

## 5. Install Dependencies

```bash
composer install
```

---

## 6. Environment Setup

Copy the example environment file:

```bash
cp .env.example .env
```

Generate the application key:

```bash
php artisan key:generate
```

Edit the `.env` file:

```bash
vim .env
```

**Vim basics (don’t mess this up):**

* Press `i` → insert mode
* Edit values
* Press `Esc`
* Type `:wq` and press `Enter` to save and exit

---

## 7. Create Symbolic Link

Create a symlink so `public_html` points to Laravel’s `public` folder:

```bash
ln -s public public_html
```

Verify:

```bash
ls -la
```

---

## 8. Run Database Migrations

Make sure database credentials in `.env` are correct **before this step**.

```bash
php artisan migrate
```

---

## Final Notes (Read This)

* Deleting everything with `rm -rf *` is **not reversible**
* Ensure correct PHP & Composer versions are installed
* Check file permissions if you hit 500 errors
* If `public_html` already exists, remove it before creating the symlink


