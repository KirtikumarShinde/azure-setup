# Azure Data Lake Analystics

#### Overview

This document covers the steps for creating Azure Data Lake Analytics.

### Features

* **SaaS** 
    
    It is SaaS (Software as a Service) from Azure for analytics. 
    The cluster creation, node assignment, load balancing is done automatically.

* **U-SQL and C#**
    
    You can only use U-SQL which is  more like  SQL. 
    The C# types & C# expressions provide more flexibility and extension if needed.
    The U-SQL works with both structured and unstructured data.

* **Multiple Read Sources**

    Can read data from many different sources like Azure SQL Warehouse, SQL db, 
    Blob storage, Azure data lake storage (gen1 only).
    
* **Write back limited**
    
    You can only write to BLOB and ADLS.
    
* **Pricing**

    Pricing is per job rather than per hour. Each job run is assigned Analytic Units(AU), 
    the price is dependant ON AU and how many hours it ran.
    
* **Visual Studio integration**
    
    You can submit queries directly on portal. Or you can use Visual studio - which allows you to write, debug and run the code. 
    Visualizations provided allow you to identify bottlenecks in the code and tune accordingly. 
    
