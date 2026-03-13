# REZOLVARE

## 1. Validarea funcționării mediului

După pornirea stack-ului cu `docker compose up -d`, am accesat interfața Adminer la adresa `http://localhost:8888` și m-am conectat la baza de date folosind:
- **System:** PostgreSQL
- **Server:** db
- **Username:** qa_user
- **Password:** qa_pass
- **Database:** qa_db

Am executat comanda SQL:
CREATE TABLE tests (id INT);
SELECT * from tests;

Folosirea flag-ului -v în comanda docker compose down -v este importantă într-un flux de lucru QA deoarece șterge și volumele asociate containerelor, nu doar containerele și rețeaua. 
Astfel, mediul este resetat complet, inclusiv datele persistente din baza de date, ceea ce permite rerularea testelor într-un mediu curat și previzibil. 
Acest lucru reduce riscul ca rezultatele testelor să fie influențate de date rămase din execuții anterioare.