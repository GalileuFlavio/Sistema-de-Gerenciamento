# Sistema-de-Gerenciamento
Sistema de Gerenciamento de Livraria
import sqlite3

conn = sqlite3.connect('livraria.db')
cursor = conn.cursor()

cursor.execute('''CREATE TABLE autores (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT NOT NULL
)''')

cursor.execute('''CREATE TABLE livros (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    titulo TEXT NOT NULL,
    autor_id INTEGER,
    FOREIGN KEY(autor_id) REFERENCES autores(id)
)''')

conn.commit()
conn.close()
