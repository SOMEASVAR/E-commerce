# Exercise-25

## Aim:

To create an E-commerce application using SpringBoot and SQL.

## Algorithm:

1.Open Spring Initialzr.

2.Save the zip file.

3.Open an IDE like IntelliJ,Oracle etc.

4.Open the folder in the IDE.

5.Create Components.

6.Connect the database with the SpringBoot.

## Program:

Ecommerce.java
```
package com.Ecom.ecom.eco;

import jakarta.persistence.*;
import org.junit.platform.commons.annotation.Testable;
import org.springframework.boot.autoconfigure.domain.EntityScan;

import java.time.LocalDate;
import java.time.Period;

@Entity
@Table
public class Ecommerce {
    @Id
    @SequenceGenerator(
            name = "ecom_sequence",
            sequenceName = "ecom_sequence",
            allocationSize = 1
    )
    @GeneratedValue(
            strategy = GenerationType.SEQUENCE,
            generator = "ecom_sequence"
    )
    private Long ecomId;
    private String ecomName;
    @Transient
    private Integer ecomAge;
    private LocalDate ecomDob;
    private String ecomEmail;

    public Ecommerce() {
    }

    public jobportal(Long ecomId, String ecomName, LocalDate ecomDob, String ecomEmail) {
        this.ecomId = ecomId;
        this.ecomName =ecomName;
        this.ecomDob = ecomDob;
        this.ecomEmail =ecomEmail;
    }

    public Long getecomId() {
        return ecomId;
    }

    public void setecomId(Long ecomId) {
        ecomId = ecomId;
    }

    public String getecomName() {
        return ecomName;
    }

    public void setecomName(String ecomName) {
       ecomName = ecomName;
    }

    public Integer getecomAge() {
        return Period.between(ecomDob,LocalDate.now()).getYears();
    }

    public void setecomAge(Integer ecomAge) {
        ecomAge = ecomAge;
    }

    public LocalDate getecomDob() {
        return ecomDob;
    }

    public void setecomDob(LocalDate ecomDob) {
        ecomDob = ecomDob;
    }

    public String getecomEmail() {
        return ecomEmail;
    }

    public void setecomEmail(String ecomEmail) {
        ecomEmail = ecomEmail;
    }

    @Override
    public String toString() {
        return "Ecommerce{" +
                "ecomId=" + ecomId +
                ", ecomName='" + ecomName + '\'' +
                ", ecomAge=" + ecomAge +
                ", ecomDob=" + ecomDob +
                ",ecomEmail='" + ecomEmail + '\'' +
                '}';
    }
}

```

applications.properties
```
spring.datasource.url=jdbc:postgresql://localhost:5432/hosman_db
spring.datasource.username=postgres
spring.datasource.password=saiabi@123
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.properties.hibernate.format_sql=true

```

App.js
```
import React from "react"
import './App.css';
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";
import ecomComponent from './components/ecomComponent/ecomComponent';
import HeaderComponent from "./components/HeaderComponent/HeaderComponent";
import ecomComponent from "./components/ecomComponent/ecomComponent";
import jobportalComponent from "./components/ecomComponent/ecomComponent";

function App() {
  return (
    <Router>
            <div className="container">
              <HeaderComponent/>
              
            <nav className="nav-menu">
                <Link to="/" >Home</Link>
                <Link to="/admin/add" >Add Member</Link>
                <Link to="/admin/delete" >Delete Member</Link>
            </nav>
           <Routes>
                 <Route exact path='/' element={<ecomComponent/>}></Route>
                 <Route path='/admin/add' element={<ecomComponent/>}></Route>
                 <Route path='/admin/delete' element={<ecomComponent/>}></Route>
          </Routes>
          </div>
       </Router>
  );
}

export default App;
```

## Output:


![Screenshot (3)](https://github.com/SaiDarshan2003/E-commerce/assets/94692595/cdc7fbb8-7090-4edb-90ff-c0c0acc99abb)



## Result:

Thus we have successfully created an E-commerce application using SpringBoot and SQL.
