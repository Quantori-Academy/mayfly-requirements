# The flow of substances and samples
The typical flow of chemicals in the Lab:

1. Researcher creates a request to buy a reagent

   ```typescript
   interface ReagentRequest {
   		id: string; // UUID
   		name: string; // Hexan, Laboratory Reagent, ≥95%
   		comments: string;
   		structure?: string; // SMILES, e.g. CCCCCC, 
   		// Note, it should be possible to search by chemical structure
   		cas?: string; // CAS, e.g. 110-54-3
   		producer?: string; // Sigma-Aldrich
   		catalogId?: string; // 208752
   		catalogLink?: string; // <https://www.sigmaaldrich.com/AT/de/product/sigald/208752>
   		units: string; // bottle 500 ml
   		pricePerUnit?: number; // 45.15$
   		quantity: number; // e.g. 6, means we buy 6 bottles 500 ml each
   	}
   ```
2. Procurement officer requests chemicals from a supplier and create an order:

```typescript
interface Order {
	title: string;
	date: Date;
	seller: string;
	itemsList: Substance[]
}
interface Substance {
		id: string; // UUID
		name: string; // Hexan, Laboratory Reagent, ≥95%
		structure?: string; // SMILES, e.g. CCCCCC, 
		// Note, it should be possible to search by chemical structure
		cas?: string; // CAS, e.g. 110-54-3
		producer: string; // Sigma-Aldrich
		catalogId?: string; // 208752
		catalogLink?: string; // <https://www.sigmaaldrich.com/AT/de/product/sigald/208752>
		units: string; // bottle 500 ml
		pricePerUnit: number; // 45.15$
		quantity: number; // e.g. 6, means we buy 6 bottles 500 ml each
	}
```

3\. When the order has arrived to the lab all chemicals should be moved to storage places:

```typescript
// a place where we can storage reagents
interface StoragePlace {
	room: string; // link to a room: Building 1, Room 15
	place: string; // e.g. 'Cabinet 1, shelf 3' or 'Frige 2, shelf 1, red box'
	items: SubstanceContainer[];
}
// Describes a specific bottle from the order. If we buy 6 bottles of hexane
// we have 6 SubstanceContainers, imagine that we stick QR code on each bottle
// to track where we bought it and how we are expending it.
interface SubstanceContainer {
  type: 'substance' | 'sample';
	itemId: string; // Substance.id or Sample.id (See below)
	units: string; // e.g. ml
	quantityLeft: number; // 250 - means only half of initial 500 ml left
}
```

4\. Researcher performs experiments, consumes reagents and creates samples from reagents:

```typescript
interface Sample {
	id: string; // UUID
	title: string; // reaction product
	description: string; // reaction description
	structure?: string; // SMILES, e.g. CCCCCC,
	reagentsList: SubstanceContainer[];
	units: string; // e.g. mg
	initialQuantity: number; // 150 mg
}
```

5\. Every sample is stored somewhere - it has own SubstanceContainer.

6\. Chemist may perform reactions using existing samples and create new samples as a result (creating a sample from the sample).

7\. Chemists may use a sample for other experiments and just make a record that SubstanceContainer.quantityLeft is decreased.

8\. When the sample or substance is completely disposed (SubstanceContainer.quantityLeft == 0) it becomes invisible in for the users.



## **Roles**

### System Administrator

* Add, delete, edit users
* Add, Delete, edit storage locations
* Configure global system parameters

### Procurement officer

* Create reagents orders
* When the order has arrived they put the items to storage locations
* They want to:
  * Track how many reagents left
  * Track monthly usage of reagents to predict future requirements

### Researcher

* Perform chemical reactions: Create samples from substances or other samples
* Perform other experiments: expend samples and substances
* Move samples and substances between storage locations
* They want to:
  * Request to buy new chemicals
  * Search for chemicals in the storage by name, structure, description
  * Track what reagents were used for creating a specific sample (track up until the [order.id](http://order.id/ "http://order.id") where the reagent has been bought)