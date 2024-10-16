See next for details: [[_I. Requirements]]

The Customer is a new but fast-growing pharmaceutical/biological/chemical company. The Customer is going to expand Research Department significantly to support increased demand for experiments and products. Current process of work is based on verbal communication because all laborants are working close to each other. With changes in Research Department current communication will eventually lead the Customer to fail goals achieving.

Considering postulates above we need to develop a LIMS (Laboratory Information Management System) to cover the following users needs:

#### System Administrator

- Add, delete, edit users and their roles
    
- Add, delete, edit storage locations (a place where reagents and sample are stored, e.g. Room 12, Cabinet 2, shelf 3)
    
- Add, delete, edit equipment and its location (e. g. Spectrometer EX151V5, Room 22)
    

#### Procurement officer

- Order reagents from suppliers (Create, edit orders)
    
- When the order has arrived they put the items to storage locations (Create, edit records about reagents)
    
- They want to:
    
    - Track how many reagents left
        
    - Track monthly usage of reagents to predict future requirements
        

#### Chemistry/Biology researcher

- Perform chemical/biological experiments: Create samples from reagents or other samples
    
- Perform other experiments: expend samples and reagents, track how many samples left
    
- Move samples and reagents between storage locations
    
- They want to:
    
    - Request to buy new chemicals
        
    - Search for chemicals in the storage by name, structure, description
        
    - Track what reagents were used for creating a specific sample (track up until the order where the reagent has been bought)

#### Test Data

- Sample list of reagents: `.\data\list_of_reagents.csv`        

#### Glossary

In the text above

- reagents - chemicals purchased from suppliers
    
- samples - substances obtained as a result of an experiment
    
- equipment - big and expensive instruments in shared usage
