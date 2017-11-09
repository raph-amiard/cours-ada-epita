% Le langage Ada
% Raphael Amiard - Adacore
% amiard@adacore.com

---

## Historique

- Dans les années 70, le DOD souffre d’une explosion du nombre des langages utilisés
- Il lance un concours international pour un langage qui répond à toutes ces exigences (1974)

---

## Historique

- Plusieurs propositions
- Vainqueur: L’équipe de Jean Ichbiah, CII Honeywell Bull
- Première normalisation du langage (ANSI, ISO): 1983
- Révisions majeures en 1995, 2005, 2012.
- L’un des seuls langages normalisés à priori

---

## Exigences du langage

- Généraliste
    * Efficacité
    * Simplicité
    * Implémentabilité

- Haut niveau de génie logiciel
    * Maintenabilité
    * Portabilité
    * Fiabilité

- Norme claire et non ambiguë
- Travail sur des plateformes embarquées
- Traitements parallèles
- Gestion des données bas niveau

---

## Résultat: Ada

- Dérivé d’une syntaxe type Pascal
- Impératif (comme Fortran, Cobol, C/C++, Java, Python...)
- Parallélisme intégré au langage (par opposition aux API type pthread)
- Modulaire (facilité de mise en place de sous-ensembles)
- Vérifications statiques et dynamiques (bornes...)

---

## Ada aujourd’hui

### Marché privilégié:

* Systèmes temps-réel
* Systèmes critiques (safety critical, mission critical)
* Systèmes de sécurité (MILS)

### Exemples

* Arianne 6
* 787 Dreamliner (Common Core System)
* Airbus A350 XWB (Air Data Inertial Reference Unit)
* Sentinel 1 (Environmental Satellite System)
* Canadian Space Arm
* Meteor (metro line 14)

---

## Exemple: Hello, World

~~~ada
with Ada.Text_IO; use Ada.Text_IO;

--  Display a welcome message
procedure Greet is
begin
    Put_Line ("Hello, world !");
end Greet;
~~~

~~~sh
$ gnatmake greet.adb
$ ./greet
~~~

# Imperative language

## Imperative language - for loops

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
begin
   for I in 1 .. 10 loop
      Put_Line("Hello, World!");
   end loop;
end Greet;
~~~

- I here denotes a constant that is only accessible in the
  loop.
- "1 .. 10" is a range.
- Put_Line is a procedure call. procedure is like a fn
  returning void in C/C++.

## Imperative language - while loops

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   --  Variable declaration. Only legal in declarative
   --  parts.
   I : Integer := 1;
begin
   --  Condition. *Must* be of type boolean
   while I < 10 loop
      Put_Line("Hello, World!");

      --  Assignment
      I := I + 1;
   end loop;
end Greet;
~~~

## Imperative language - General loops

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   I : Integer := 1;
begin
   loop
      Put_Line("Hello, World!");
      exit when I = 5;
      --  Exit statement - takes a boolean condition
      I := I + 1;
   end loop;
end Greet;
~~~


## Imperative language - If

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   I : Integer := 1;
begin
   loop
      Put_Line("Hello, World!");
      if I = 5 then
         exit;
      end if;
      I := I + 1;
   end loop;
end Greet;
~~~

## Imperative language - If/Else

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   I : Integer := 1;
begin
   loop
      if I = 5 then
         exit;
      else
         Put_Line("Hello, World!");
      end if;
      I := I + 1;
   end loop;
end Greet;
~~~

## Imperative language - If/Elsif/Else

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   I : Integer := 0;
begin
   loop
      if I = 5 then
         exit;
      elsif I = 0 then
         Put_Line (“Starting...”);
      else
         Put_Line ("Hello, World!");
      end if;
      I := I + 1;
   end loop;
end Greet;
~~~

## Imperative language - If/Else

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   I : Integer := 1;
begin
   loop
      --  "or else" is the short circuit or operator
      if I = 5 or else I = 2 then
         exit;
      else
         Put_Line("Hello, World!");
      end if;
      I := I + 1;
   end loop;
end Greet;
~~~

## Imperative language - If/Else

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
procedure Greet is
   I : Integer := 1;
begin
   loop
      --  "and then" is the short circuit or operator
      if I < 5 and then I > 2 then
         exit;
      else
         Put_Line("Hello, World!");
      end if;
      I := I + 1;
   end loop;
end Greet;
~~~

## Imperative language - Case statement

~~~ada
procedure Greet is
   I : Integer := 0;
begin
   loop
      -- Expression must be of a discrete type. All the
      -- values must be covered.
      case I is
         when 0 => Put_Line (“Starting...”);
         when 3 .. 4 => Put_Line (“Hello”);
         when 7 | 9 => exit;
         -- ‘when others’ must be the last one and alone (if
         -- present)
         when others => Put_Line ("Hello, World!");
      end case;
      I := I + 1;
   end loop;
end Greet;
~~~

# Quizz

## Quizz 1: Is there a compilation error ?

~~~ada
for I in 10 .. 1 loop
    Put_Line("Hello, World!");
end loop;
~~~

## Quizz 2: Is there a compilation error ?

~~~ada
for I in reverse 1 .. 10 loop
    Put_Line("Hello, World!");
end loop;
~~~

## Quizz 3: Is there a compilation error ?

~~~ada
procedure Hello is
   I : Integer;
begin
   for I in 1 .. 10 loop
      Put_Line ("Hello, World!");
   end loop;
end Hello;
~~~

## Quizz 4: Is there a compilation error ?

~~~ada
with Ada.Text_IO; use Ada.Text_IO;

procedure Greet is
   I : Integer;
begin
   while I < 10 loop
      Put_Line("Hello, World!");
      I := I + 1;
   end loop;
end Greet;
~~~

## Quizz 5: Is there a compilation error ?

~~~ada
with Ada.Text_IO; use Ada.Text_IO;

procedure Greet is
    I : Integer := 2;
begin
    while i < 10 loop
        Put_Line ("Hello, World!");
        i := i + 1;
    end loop;
end Greet;
~~~

## Quizz 6: Is there a compilation error ?

~~~ada
with Ada.Text_IO; use Ada.Text_IO;
with Tools;

procedure Greet is
begin
    loop
        Put_Line("Hello, World!");
        Tools.My_Proc;
    end loop;
end Greet;
~~~
