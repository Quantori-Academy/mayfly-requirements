|                                                                                                                                                           | **MoSCoW**  |
| --------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| The first stage                                                                                                                                           |             |
| User Authentication                                                                                                                                       |             |
| As a user, I want to be able to log in to my account                                                                                                      | Must have   |
| As an administrator, I want to be able to add new users to the system so that they can access the application                                             | Must have   |
| As an administrator, I want to be able to reset user's password                                                                                           | Should have |
| As an administrator, I want to be able to delete users so that they can no longer access the application                                                  | Could have  |
| As an administrator, I want to be able to edit user role                                                                                                  | Must have   |
| As a user, I want to be able to reset my password if I forget it                                                                                          | Could have  |
| As a backend developer, I want to implement user authentication.                                                                                          | Must have   |
| As a backend developer, I want to implement password reseting workflow.                                                                                   | Must have   |
| As a backend developer, I want to implement middleware for verifying JWT tokens on protected routes.                                                      | Must have   |
| As a backend developer, I want to handle token expiration and renewal                                                                                     | Must have   |
| Order Management                                                                                                                                          |             |
| As a procurement officer, I want to be able to create a new order for reagents                                                                            | Must have   |
| As a backend developer, I want to create endpoints for managing orders (CRUD operations).                                                                 | Must have   |
| As a procurement officer, I want to be able to see a list of reagent requests and create an order from them                                               | Should have |
| As a researcher, I want to be able to create a reagent request                                                                                            | Must have   |
| As a backend developer, I want to create endpoints for managing reagent requests (CRUD operations).                                                       | Must have   |
| As a researcher, I want to be able to see my reagent request status                                                                                       | Must have   |
| As a procurement officer, I want to be able to decline reagent request with a comment                                                                     | Must have   |
| As a procurement officer, I want to be able to view existing orders                                                                                       | Must have   |
| As a procurement officer, I want to be able to edit existing order                                                                                        | Must have   |
| As a procurement officer, I want to be able to mark an order as completed when the reagents have been received and stored                                 | Must have   |
| As a backend developer, I want to implement logic for tracking order status (e.g., pending, completed).                                                   | Must have   |
| Reagent Search                                                                                                                                            |             |
| As a user, I want to be able to search for reagents by name, structure, or description                                                                    | Must have   |
| As a backend developer, I want to create endpoints for managing reagents (CRUD operations).                                                               | Must have   |
| As a backend developer, I want to implement search of reagents by structure and substructure                                                              | Must have   |
| As a user, I want to be able to view detailed information about a specific reagent                                                                        | Must have   |
| As a procurement officer, I want to be able to view reports on the usage of reagents so that the system I can identify trends and buy reagents in advance | Should have |
| Storage Management                                                                                                                                        |             |
| As an administrator, I want to be able to add, edit storage locations                                                                                     | Must have   |
| As an administrator, I want to be able to delete storage locations                                                                                        | Must have   |
| As a user, I want to be able to view the contents of each storage location                                                                                | Must have   |
| As a user, I want to be able to move items between storage locations                                                                                      | Must have   |
| As a backend developer, I want to create endpoints for managing storage locations (CRUD operations).                                                      | Must have   |
| Sample Management                                                                                                                                         |             |
| As a chemist, I want to be able to create a new sample from reagents or other samples                                                                     | Must have   |
| As a backend developer, I want to create endpoints for managing samples (CRUD operations).                                                                | Must have   |
| As a backend developer, I want to implement search of samples by structure and substructure                                                               | Must have   |
| As a chemist, I want to be able to view existing samples                                                                                                  | Must have   |
| As a chemist, I want to be able to search samples by name, structure, or description                                                                      | Must have   |
| As a chemist, I want to be able to decrease sample quantity                                                                                               | Must have   |
| As a chemist, I want to be able to decrease reagent quantity                                                                                              | Must have   |
| As a user, I want to find all expired samples and trash them                                                                                              | Should have |
| Dashboard                                                                                                                                                 |             |
| As a user, I want to see a dashboard with relevant information such as recent orders, reagent usage statistics, etc.                                      | Could have  |