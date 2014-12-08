LanguageDatabase
================

Design a Java Swing user interface to access the SSDI data of US social security numbers. The program is to be an application (not an applet). A read-only database of information will be provided for you. You must use JDBC to access it. The application is to make it easy for someone that does not know SQL to search the database.
Perhaps the single most important GUI design principle is that the GUI must look and function well at any reasonable size. In particular, a GUI must be resizable to find the unknown display requirements of the users. So, even if the window allowed your GUI is smaller than you would like the GUI should still be useful. Put

mysql-connector-java-5.1.27-bin.jar
on the classpath.
Information needed to access the database I am running for this project:

jdbc:mysql://andrew.cs.fit.edu:3306/cse4051_ssdi?user=cse4051&password=jdbc
The actual password will be announced in class.
Example SQL queries that work on MySQL (but not on this database!).

SELECT * FROM families WHERE (name REGEXP "^J" AND speakers >=10000) ORDER BY name
SELECT name,speakers,family FROM families WHERE speakers >=10000 ORDER BY name
SELECT name,speakers,family FROM families WHERE (speakers >=100000 AND speakers <=200000) ORDER BY name
SELECT name,speakers,family FROM families WHERE speakers BETWEEN 100000 AND 200000 ORDER BY name;
SELECT name,speakers,family,fips FROM languages,countries WHERE countries.code=languages.code and (name REGEXP "^J" AND speakers <=10000) ORDER BY name
SELECT DISTINCT family FROM languages ORDER BY family;
SELECT alias, languages.* from sil.aliases,sil.languages where sil.aliases.code=sil.languages.code and aliases.alias LIKE "%obo%";
SELECT * from sil.aliases where alias LIKE "%cantonese%";

LIKE and REGEXP searches ignore case.
Data

The catalog or "database" is cse4051_ssdi, there is just one table index. Since the name of the table is a reserved identifier in SQL is is necessary to escape the name in SQL syntax. The backquote worked in MySQL: `index`. Please observe the case, as it is also significant. The columns of the tables are
column	description
number	unique social security number
last	last or family name
suffix	e.g., Jr., Sr., or IV
first	first
middle	middle name or initial
death	date of death as a string (sometimes month and year only)
birth	date of birth as a string
All columns are VARCHAR


CSE 4051 project 11
