
create table if not exists users
(
    id        serial primary key,
    name      varchar(255)        not null default '',
    last_name varchar(255)        not null default '',
    work      varchar(255)        not null default '',
    email     varchar(255) UNIQUE not null default '',
    work_id   int,
    price     NUMERIC,
    primary key (id),
    UNIQUE (email)

);

create table if not exists works
(
    id      serial primary key,
    works_name varchar(255) not null default '',
    status     bool
);

create table if not exists timing
(
    id      serial primary key,
    code    varchar(255) not null default '',
    track   uuid,
    work_id int
);

insert into users (name, last_name, email, price)
VALUES ('migin', 'dmitriy', 'igor.migin@mail.ru', '55000'),
       ('mixail', 'ryibov', 'mihail.ryabov.2002@mail.ru', '40000'),
       ('anton', 'ershov', 'ahtoika12@gmail.com','60000'),
       ('danila', 'petrukhin', 'danilapetrukhin@mail.ru', '68000'),
       ('daniil', 'kirsanov', 'hvck1337@yandex.ru', '70000'),
       ('vlad', 'kirsanov', 'wladnext98@mail.ru','50000'),
       ('jaroslav', 'mihailov', 'tosha.zakharov.0201@mail.ru', '48000');

select DISTINCT id, name, last_name,email,price
from users
ORDER BY price ASC;
