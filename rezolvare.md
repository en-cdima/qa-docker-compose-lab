# REZOLVARE

## 1. Set-up initial si pornirea mediului

După pornirea stack-ului cu `docker compose up -d`, am accesat interfața Adminer la adresa `http://localhost:8888` și m-am conectat la baza de date folosind:
- **System:** PostgreSQL
- **Server:** db
- **Username:** qa_user
- **Password:** qa_pass
- **Database:** qa_db

## 2. Validarea functionarii in Adminer

Pentru verificarea stării containerelor am rulat:

docker compose ps

Rezultatul arată că toate containerele rulează și că serviciul db are statusul healthy, ceea ce confirmă că baza de date este pregătită să accepte conexiuni.

## 3. Validarea functionarii in Adminer si resetarea completa a mediului

Am executat comanda SQL:
CREATE TABLE tests (id INT);
SELECT * from tests;

Pentru oprirea și resetarea completă a mediului de testare am folosit comanda:

docker compose down -v

Aceasta oprește containerele, șterge rețeaua creată de Docker Compose și elimină volumul db-data, resetând complet mediul de test.