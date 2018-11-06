create database libary_management
use libary_management

create table authors(
    id int identity primary key,
	name varchar(50) unique not null
);

create table categorias(
	id int identity primary key,
	name varchar(50) unique not null
);

create table publishers (
	id int identity primary key,
	name varchar(50) unique not null
);

create table books(
	id int identity primary key,
	documenttype varchar(50),
	title varchar(50) not null,
	isbn10 numeric(20) unique,
	isbn13 numeric(20) unique,
	issn numeric(20) unique,
	doi numeric(20) unique,
	year int not null,
	cota varchar(20),
	local varchar(20),
	abstract varchar(MAX)
);

create table copies(
	id int identity primary key,
	number numeric(10) unique not null,
	status int
);

create table requests(
	id int identity primary key,
	status varchar(50) not null,
	startdate datetime default getdate(),
	enddate datetime
);

create table users(
	id int identity primary key,
	username varchar(20) unique not null,
	password varchar(MAX) not null,
	name varchar(50),
	email varchar(50),
	address varchar(100),
	phone numeric(10),
	birthdate date,
	gender varchar(10),
	accesslevel int not null default 0
);

create table author_book(
	fk_book int foreign key references books(id) not null,
	fk_author int foreign key references authors(id) not null,
);

create table request_copie(
	fk_request int foreign key references requests(id) not null,
	fk_copie int foreign key references copies(id) not null,
);

create table categorie_book(
	fk_categorie int foreign key references categorias(id) not null,
	fk_book int foreign key references books(id) not null
);

alter table books
	add fk_publisher int foreign key references publishers(id)

alter table requests
	add fk_user int foreign key references users(id)

alter table copies
	add fk_book int foreign key references books(id)
