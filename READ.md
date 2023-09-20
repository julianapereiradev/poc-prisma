# poc-prisma

## Tabelas em SQL

- Pelo menos 3 entidades
- Pelo menos 2 entidades com relacionamento 1:1 ou 1:N ou N:M

---

1 ENTIDADE: GAMES

CREATE TABLE games (
    id serial PRIMARY KEY,
    title text,
    platform_id integer NOT NULL REFERENCES platforms(id)
);

---

2 ENTIDADE: PLATFORMS

CREATE TABLE platforms (
    id serial PRIMARY KEY,
    name text NOT NULL
);


---

3 ENTIDADE: USERS

CREATE TABLE users (
    id serial PRIMARY KEY,
    firstName text NOT NULL,
    lastName text NOT NULL,
    game_id integer NOT NULL REFERENCES games(id)
);

