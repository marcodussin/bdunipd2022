-- MySQL dump 10.13  Distrib 5.6.11, for osx10.7 (x86_64)
--
-- Host: localhost    Database: universita
-- ------------------------------------------------------
-- Server version	5.6.11

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `corso`
--

DROP TABLE IF EXISTS `corso`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `corso` (
  `codice` varchar(5) NOT NULL DEFAULT '',
  `nome` varchar(30) DEFAULT NULL,
  PRIMARY KEY (`codice`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `corso`
--

LOCK TABLES `corso` WRITE;
/*!40000 ALTER TABLE `corso` DISABLE KEYS */;
INSERT INTO `corso` VALUES ('bd1','Basi di dati 1'),('ec1','Economia 1'),('se1','Sistemi di elaborazione 1'),('st1','Statistica 1'),('st2','Statistica 2');
/*!40000 ALTER TABLE `corso` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `docente`
--

DROP TABLE IF EXISTS `docente`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `docente` (
  `matricola` smallint(3) NOT NULL DEFAULT '0',
  `cognome` varchar(30) NOT NULL DEFAULT '',
  `nome` varchar(20) DEFAULT NULL,
  `indirizzo` varchar(50) DEFAULT NULL,
  `ora_ricevimento` time DEFAULT NULL,
  PRIMARY KEY (`matricola`),
  UNIQUE KEY `cognome` (`cognome`,`nome`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `docente`
--

LOCK TABLES `docente` WRITE;
/*!40000 ALTER TABLE `docente` DISABLE KEYS */;
INSERT INTO `docente` VALUES (1,'Consoli','Maria','Dip. di Matematica','10:15:00'),(2,'Comicini','Paola','Dip. di Economia','08:30:00'),(3,'Alessandrini','Vincenzo','Dip. di Informatica','19:00:00'),(4,'Marchesini',NULL,'Dip. di Statistica','12:30:00'),(5,'Salvatori','Concetta',NULL,'10:45:00');
/*!40000 ALTER TABLE `docente` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `esame`
--

DROP TABLE IF EXISTS `esame`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `esame` (
  `studente` int(6) NOT NULL,
  `voto` int(2) DEFAULT NULL,
  `lode` tinyint(1) DEFAULT NULL,
  `registrazione` date NOT NULL,
  `corso` varchar(5) NOT NULL,
  `docente` smallint(3) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `esame`
--

LOCK TABLES `esame` WRITE;
/*!40000 ALTER TABLE `esame` DISABLE KEYS */;
INSERT INTO `esame` VALUES (1,28,NULL,'2002-09-11','se1',1),(2,27,NULL,'2001-07-13','bd1',2),(1,30,1,'2001-07-01','ec1',3),(3,27,NULL,'2002-08-23','st1',4),(2,NULL,NULL,'2002-07-18','st2',5),(1,30,0,'2001-06-20','ec1',3),(4,30,0,'2002-09-19','st2',5),(1,25,NULL,'2001-02-10','bd1',2),(2,30,0,'2001-05-12','se1',1),(1,23,NULL,'2002-08-01','st2',5),(3,30,1,'2002-07-22','st2',5),(2,NULL,NULL,'2001-04-17','st1',4),(1,29,NULL,'2002-02-21','ec1',3),(4,28,NULL,'2002-01-18','st2',5);
/*!40000 ALTER TABLE `esame` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `studente`
--

DROP TABLE IF EXISTS `studente`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `studente` (
  `matricola` int(6) NOT NULL DEFAULT '0',
  `cognome` varchar(30) NOT NULL DEFAULT '',
  `nome` varchar(10) DEFAULT NULL,
  `sesso` char(1) DEFAULT NULL,
  `nascita` date DEFAULT NULL,
  `media` decimal(4,2) DEFAULT NULL,
  PRIMARY KEY (`matricola`),
  UNIQUE KEY `cognome` (`cognome`,`nome`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `studente`
--

LOCK TABLES `studente` WRITE;
/*!40000 ALTER TABLE `studente` DISABLE KEYS */;
INSERT INTO `studente` VALUES (1,'Rossi','Mario','M','1990-08-10',21.90),(2,'Bianchi','Paola','F','1989-07-22',NULL),(3,'Verdi',NULL,NULL,'1991-09-06',29.90),(4,'Azzurri','Luisa','F',NULL,18.60);
/*!40000 ALTER TABLE `studente` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2015-05-18 11:04:54
