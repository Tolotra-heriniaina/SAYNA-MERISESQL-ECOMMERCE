https://app.diagrams.net/#G1CSjUM8HueR7vE1pirx06gtE8V3ot8g7Y#%7B%22pageId%22%3A%22SAl5dh8H6KVTbhCNLUOq%22%7D

	CREATE DATABASE Ecommerce;
	SHOW DATABASES;
	CREATE TABLE Client (
    ID_client INT PRIMARY KEY AUTO_INCREMENT,
    Nom VARCHAR(255) NOT NULL,
    Prénom VARCHAR(255) NOT NULL,
  	Ville VARCHAR (255),
  	Rue VARCHAR(255),
    Adresse_email VARCHAR(255) UNIQUE NOT NULL,
    Numéro_téléphone VARCHAR(255),
  	Code_Postal VARCHAR (255),
  	Pays VARCHAR (255)
);
	CREATE TABLE Catégorie (
    ID_catégorie INT PRIMARY KEY AUTO_INCREMENT,
    Nom_catégorie VARCHAR(255) NOT NULL,
    Description_catégorie TEXT
);

	CREATE TABLE Utilisateur (
    ID_utilisateur INT PRIMARY KEY AUTO_INCREMENT,
    Nom_utilisateur VARCHAR(255) UNIQUE NOT NULL,
    Mot_de_passe VARCHAR(255) NOT NULL,
    Rôle ENUM('utilisateur normal', 'administrateur') NOT NULL
);

	CREATE TABLE Produit (
    ID_produit INT PRIMARY KEY AUTO_INCREMENT,
    Nom_produit VARCHAR(255) NOT NULL,
    Description TEXT,
    Prix DECIMAL(10, 2) NOT NULL,
    ID_catégorie INT,
    Stock_disponible INT NOT NULL,
    FOREIGN KEY (ID_catégorie) REFERENCES Catégorie(ID_catégorie)
);

	CREATE TABLE Commande (
    ID_commande INT PRIMARY KEY AUTO_INCREMENT,
    ID_client INT,
    order_at DATETIME NOT NULL,
    delivred_at DATETIME,
  	amount INT NOT NULL,
    FOREIGN KEY (ID_client) REFERENCES Client(ID_client)
);

INSERT INTO client (Nom, Prénom, Ville, Rue, Adresse_email, Numéro_téléphone, Code_Postal, Pays)
VALUES
    ('John', 'Doe', 'New York', '123 Main St', 'john.doe@example.com', '123-456-7890', '10001', 'USA'),
    ('Jane', 'Smith', 'Los Angeles', '456 Elm St', 'jane.smith@example.com', '987-654-3210', '90001', 'USA'),
    ('Alice', 'Johnson', 'Chicago', '789 Oak St', 'alice.johnson@example.com', '555-555-5555', '60601', 'USA'),
    ('Bob', 'Williams', 'Houston', '567 Pine St', 'bob.williams@example.com', '111-222-3333', '77001', 'USA'),
    ('Eva', 'Martin', 'Miami', '234 Beach Rd', 'eva.martin@example.com', '777-888-9999', '33101', 'USA');

INSERT INTO Client (Nom, Prénom, Ville, Rue, Adresse_email, Numéro_téléphone, Code_Postal, Pays)
VALUES
    ('Kwesi', 'Amissah-Arthur', 'Cape Coast', 'Pedu Rd', 'kwesi.arthur@example.com', '233-244-567890', '00233', 'Ghana'),
    ('Isabel', 'Dos Santos', 'Luanda', 'Miramar', 'isabel.dos.santos@example.com', '244-926-123456', '1000', 'Angola'),
    ('Idriss', 'Déby', 'N_Djamena', 'Presidential Palace', 'idriss.deby@example.com', '235-662-111222', '01 BP 109', 'Chad'),
    ('Marc', 'Ravalomanana', 'Antananarivo', 'Iavoloha', 'marc.ravalomanana@example.com', '261-20-1234567', '101', 'Madagascar'),
    ('Ntsay', 'Christian', 'Antananarivo', 'Ambohitsorohitra', 'christian.ntsay@example.com', '261-20-9876543', '101', 'Madagascar'),
    ('Jean', 'Rajaonarimampianina', 'Antananarivo', 'Iavoloha', 'jean.rajaonarimampianina@example.com', '261-20-5555555', '101', 'Madagascar'),
    ('Andry', 'Rajoelina', 'Antananarivo', 'Ambohitsorohitra', 'andry.rajoelina@example.com', '261-20-7777777', '101', 'Madagascar'),
    ('Hery', 'Rajaonarimampianina', 'Antananarivo', 'Iavoloha', 'hery.rajaonarimampianina@example.com', '261-20-8888888', '101', 'Madagascar'),
    ('Didier', 'Ratsiraka', 'Toamasina', 'Toamasina I', 'didier.ratsiraka@example.com', '261-53-1234567', '501', 'Madagascar');





INSERT INTO Client (Nom, Prénom, Ville, Rue, Adresse_email, Numéro_téléphone, Code_Postal, Pays)
VALUES
    ('Kwame', 'Nkrumah', 'Accra', '1 Independence Ave', 'kwame.nkrumah@example.com', '233-244-123456', 'GA1', 'Ghana'),
    ('Nelson', 'Mandela', 'Johannesburg', '46664 Vilakazi St', 'nelson.mandela@example.com', '27-123-456789', '2000', 'South Africa'),
    ('Haile', 'Selassie', 'Addis Ababa', 'Imperial Palace', 'haile.selassie@example.com', '251-911-987654', '1000', 'Ethiopia'),
    ('Wangari', 'Maathai', 'Nairobi', 'Karura Forest', 'wangari.maathai@example.com', '254-722-555555', '00100', 'Kenya'),
    ('Léopold', 'Sédar Senghor', 'Dakar', 'Avenue Léopold Sédar Senghor', 'leopold.senghor@example.com', '221-777-111222', 'BP 98', 'Senegal'),
    ('Chinua', 'Achebe', 'Enugu', '5 Ogidi Rd', 'chinua.achebe@example.com', '234-802-234567', '400001', 'Nigeria'),
    ('Ellen', 'Johnson Sirleaf', 'Monrovia', 'Executive Mansion', 'ellen.sirleaf@example.com', '231-886-987654', '1000', 'Liberia'),
    ('Kofi', 'Annan', 'Kumasi', '14 July 1993 Rd', 'kofi.annan@example.com', '233-277-765432', '00233', 'Ghana'),
    ('Desmond', 'Tutu', 'Cape Town', 'Anglican Archbishop_s Residence', 'desmond.tutu@example.com', '27-828-111111', '8001', 'South Africa'),
    ('Mansa', 'Musa', 'Timbuktu', 'Golden Palace', 'mansa.musa@example.com', '223-999-888777', '32000', 'Mali'),
    ('Yaa', 'Asantewaa', 'Kumasi', 'Golden Stool Palace', 'yaa.asantewaa@example.com', '233-544-777888', '00233', 'Ghana'),
    ('Jomo', 'Kenyatta', 'Nairobi', 'State House Rd', 'jomo.kenyatta@example.com', '254-722-987654', '00100', 'Kenya'),
    ('Amílcar', 'Cabral', 'Bissau', 'Avenida Amílcar Cabral', 'amilcar.cabral@example.com', '245-955-123456', '1004', 'Guinea-Bissau'),
    ('Amina', 'of Zazzau', 'Zaria', 'Zazzau Royal Palace', 'amina.zazzau@example.com', '234-906-876543', '810211', 'Nigeria'),
    ('Paul', 'Kagame', 'Kigali', 'Village Urugwiro', 'paul.kagame@example.com', '250-788-987654', '250', 'Rwanda'),
    ('Hassan', 'II', 'Rabat', 'Royal Palace of Rabat', 'hassan.ii@example.com', '212-661-555555', '10000', 'Morocco');
    
   INSERT INTO commande (order_at, delivred_at, amount, ID_client)
VALUES
    ('2023-08-01 10:00:00', '2023-08-02 15:00:00', 1450, 1),
    ('2023-08-02 11:30:00', '2023-08-03 14:45:00', 200, 2),
    ('2023-08-03 09:15:00', '2023-08-04 12:30:00', 50, 3),
    ('2023-08-04 13:00:00', '2023-08-05 16:15:00', 30320, 4),
    ('2023-08-05 14:30:00', '2023-08-06 18:30:00', 100, 5),
    ('2023-08-06 10:45:00', '2023-08-07 13:45:00', 725, 6),
    ('2023-08-07 12:00:00', '2023-08-08 15:15:00', 2240, 7),
    ('2023-08-08 08:15:00', '2023-08-09 11:30:00', 180, 8),
    ('2023-08-09 14:00:00', '2023-08-10 17:30:00', 9054, 9),
    ('2023-08-10 09:30:00', '2023-08-11 12:45:00', 120, 10),
    ('2023-08-11 11:45:00', '2023-08-12 14:30:00', 2350, 11),
    ('2023-08-12 13:30:00', '2023-08-13 16:15:00', 7450, 12),
    ('2023-08-13 15:00:00', '2023-08-14 18:30:00', 180, 13),
    ('2023-08-14 10:15:00', '2023-08-15 13:45:00', 160, 14),
    ('2023-08-15 12:30:00', '2023-08-16 15:15:00', 9540, 15),
    ('2023-08-16 08:45:00', '2023-08-17 11:30:00', 200, 16),
    ('2023-08-17 14:15:00', '2023-08-18 17:30:00', 1310, 17),
    ('2023-08-18 09:00:00', '2023-08-19 12:45:00', 130, 18),
    ('2023-08-19 10:45:00', '2023-08-20 13:30:00', 750, 19),
    ('2023-08-20 13:30:00', '2023-08-21 16:15:00', 2050, 20);
    
    INSERT INTO commande (order_at, delivred_at, amount, ID_client)
VALUES
    ('2023-08-01 10:00:00', '2023-08-02 15:00:00', 1450, 1),
    ('2023-08-02 11:30:00', '2023-08-03 14:45:00', 200, 2),
    ('2023-08-03 09:15:00', '2023-08-04 12:30:00', 50, 3),
    ('2023-08-04 13:00:00', '2023-08-05 16:15:00', 30320, 4),
    ('2023-08-05 14:30:00', '2023-08-06 18:30:00', 100, 5),
    ('2023-08-06 10:45:00', '2023-08-07 13:45:00', 725, 6),
    ('2023-08-07 12:00:00', '2023-08-08 15:15:00', 2240, 7),
    ('2023-08-08 08:15:00', '2023-08-09 11:30:00', 180, 8),
    ('2023-08-09 14:00:00', '2023-08-10 17:30:00', 9054, 9),
    ('2023-08-10 09:30:00', '2023-08-11 12:45:00', 120, 10),
    ('2023-08-11 11:45:00', '2023-08-12 14:30:00', 2350, 11),
    ('2023-08-12 13:30:00', '2023-08-13 16:15:00', 7450, 12),
    ('2023-08-13 15:00:00', '2023-08-14 18:30:00', 180, 13),
    ('2023-08-14 10:15:00', '2023-08-15 13:45:00', 160, 14),
    ('2023-08-15 12:30:00', '2023-08-16 15:15:00', 9540, 15),
    ('2023-08-16 08:45:00', '2023-08-17 11:30:00', 200, 16),
    ('2023-08-17 14:15:00', '2023-08-18 17:30:00', 1310, 17),
    ('2023-08-18 09:00:00', '2023-08-19 12:45:00', 130, 18),
    ('2023-08-19 10:45:00', '2023-08-20 13:30:00', 750, 19),
    ('2023-08-20 13:30:00', '2023-08-21 16:15:00', 2050, 20);
    
    
  -- Sélection de toutes les données d'une table
    SELECT * FROM client;
    
  -- Sélection de données spécifiques d'une table
    SELECT 21, Numéro_téléphone FROM client;
    
  -- Sélection avec tri et limitation de résultats
    SELECT * FROM Commande
ORDER BY order_at DESC
LIMIT 100;

	-- Recherche avec une condition
	SELECT * FROM Client
WHERE Adresse_email = 'leopold.senghor@example.com';

	-- Utilisation de fonctions d'agrégation (somme, moyenne, comptage)
  SELECT SUM(Prix) AS Total_Prix FROM Produit;
  SELECT AVG(Prix) AS Prix_Moyen FROM Produit;
  SELECT COUNT(*) AS Nombre_Commandes FROM Commande;
  
  -- Jointure de deux tables
  SELECT c.Nom, c.Prénom, o.delivred_at
FROM Client c
JOIN Commande o ON c.ID_client = o.ID_client

	-- Groupement de données avec agrégation
  SELECT ID_catégorie, COUNT(*) AS Nombre_Produits
FROM Produit
GROUP BY ID_catégorie;

	-- Mise à jour de données dans une table
  UPDATE Produit
SET Prix = Prix * 1.10
WHERE ID_catégorie = 1;  -- Augmente le prix de 10% pour la catégorie 1

	-- Insertion de nouvelles données dans une table
  INSERT INTO Client (Nom, Prénom, Ville, Rue, Adresse_email, Numéro_téléphone, Code_Postal, Pays)
VALUES ('Eva', 'Martin', 'Miami', '234 Beach Rd', 'eva.martin@example.com', '777-888-9999', '33101', 'USA');

	-- Suppression de données dans une table
  DELETE FROM Produit
WHERE ID_produit = 5;
