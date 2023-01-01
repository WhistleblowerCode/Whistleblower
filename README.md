# Whistleblower

## Introduction

Whistleblower is a cross-facility syndrome-based early warning system for unknown/limited-known epidemics. This repo contains the implementation of Whistleblower prototype and the database that stored the data set used in the experiments.

- `./Whistleblower`: includes the implementation of Whistleblower prototype.
- `./DataSet`: includes the database used to evaluate the accuracy of early warning.

## Dependencies

- Basic packages: 
  - jna-3.2.5
  - jpbc-api-1.0
  - jpbc-benchmark-2.0.0
  - jpbc-crypto-2.0.0
  - jpbc-mm-2.0.0
  - jpbc-pbc-2.0.0
  - jpbc-plaf-2.0.0
  - c3p0-0.9.5.2
  - commons-codec-1.15
  - mysql-connector-java-8.0.25

The packages above can be installed by configuring `maven` in the project or downloaded from [link](https://mvnrepository.com) and further installed in the project.

## Build & Usage

> JAVA version: 15 
>
> We recommend JAVA 8 and the later versions for building the project.

1. Create a mysql database according to the following setting

   **Database**: Whistleblower

   **Table**: Symptoms

   **Columns**: 

    - SymptomID  `int (Not null, Auto inc, Primary key)`
    - Symptom  `tinytext`
    - Code  `char(255)`

2. Change the following strings in `./Whistleblower/src/main/java/utils/JDBCTools` according to the configuration of the database.

   - JDBC_DRIVER: path of the JDBC driver

     > Ver. 8.0.25 is recommended

   - DB_URL: url of the created database

   - USER: username of the user accessing the database

   - PASS: password corresponding to the username

3. Run ``./Whistleblower/src/main/java/SymptomGen` to generate experimental data set.

Then the prototype is ready to be tested. The usage of each `.java` file is detiled below.

- `./Whistleblower/src/main/java/HelParGen`: generate helper parameters
- `./Whistleblower/src/main/java/Main`: configure system parameters and all functions of the prototype can be tested
- `./Whistleblower/src/main/java/utils/BlomFilter`: count similar symptom lists
- `./Whistleblower/src/main/java/utils/BlomFilter`: compute the explicit threshold $T$


