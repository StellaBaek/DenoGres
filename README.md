![](/public/DenoGresWide.png) Welcome to DenoGres! A new comprehensive ORM for
PostgreSQL and Deno.

## Getting Started

To begin, let's download DenoGres! Execute the below in the terminal - this will
give you access to DenoGres's CLI functionality.

> `deno install --allow-read --allow-write --allow-net --allow-env --allow-run --name denogres https://deno.land/x/denogres/mod.ts`

After installation is complete, ensure deno is added to PATH.

## Quick Start

Before using DenoGres in a project, run the command below.

> `denogres --init`

This will create the following in your project's root directory:

- .env file for your database connection URI
- a models folder for your model.ts file
- a Migrations folder for migration logs and model snapshots

After running the init command, update the .env file to contain your database's
connection URI.

> `DATABASE_URI=driver://user:password@host:port/database_name`

With all the set-up steps complete, you're ready to introspect your database!
Database introspection will automatically create TypeScript models of your
database tables in the .models/model.ts file.

> `denogres --db-pull`

## Synchronizing your Database

Denogres features bi-directional synchronization that is designed to ensure that
your database schema and your project Models in full alignment, maintaining a
single, consistent source of truth.

To introspect and generate the associated models within the model.ts file,
execute the the following CLI command:

> `denogres --db-pull`

In addition to --db-pull, Denogres also includes --db-sync functionality that
will revise the PostgreSQL schema to reflect changes within the DenoGres
model.ts file.

Once completed changes to your model have been made, execute the following CLI
command:

> `denogres --db-sync`

## Seeding Your Database

DenoGres allows data to be populated to the PostgreSQL schema through data
seeding. This is primarily useful during database design/development (i.e. an
application requires a certain amount of data to function properly) Create a
seed.ts within the project root directory, and execute the following CLI
command:

> `denogres --db-seed`

The associated database schema will be pre-populated based on the user's seed.ts
file.

## Navigating the GUI

DenoGres includes a GUI that allows the user to test and run queries utilizing
generated Models and associated methods. Furthermore, users can save database
connections and previous queries to their accounts for later access.

Launch the DenoGres GUI by running the following CLI command:

> `denogres --gui`


![alt text](/denogres-gui/src/assets/NavBarImage.jpg?raw=true "NavBar")

## Connections

The Connections page allows users to connect to any database after providing its
credentials. User can add and save multiple databases, but are only allowed to have
one active connection at a time.

![](/denogres-gui/src/assets/Connections.gif)

## Console

The Console page allows users to run database queries as needed. They can also be
saved for later use.

![](/denogres-gui/src/assets/Console.gif)

The Console page also features active models for your databse tables. This allows 
users to have a reference when inputting query strings properly.

![](/denogres-gui/src/assets/Model.gif)

## Diagram

The Diagram page offers a live ERD which visualizes the database for the user.
This includes relational mapping for all of the database tables.

Some key features of the ERD are its ability to be adjusted to the user's preference with
a live interface and the ability to save the diagram as an image.

![](/denogres-gui/src/assets/ReactFlow.gif)


## Migration Logs and Restore

Any time a user opts to make a request for --db-pull or --db-sync, Denogres
maintains a record of that request so that users can refer back to those
historical records. Additionally, users can opt to restore the Model/database
schema to prior iterations, in instances where users would like to roll
back/forward changes that have been made.

To see a historical list of migration logs, execute the following CLI command:

> `denogres --log`

To restore Models to a prior version, execute the following CLI command:

> `denogres --restore [PREVIOUS_MODEL_FOLDER]`

## Under Development

DenoGres is continually evolving. Features currently in development include:

- Database sync method (`denogres --db-sync`) will account for multiple
  associations and composite unique keys.
- "Compare" command (`denogres --compare`) will be implemented to display
  side-by-side diff between previous models.
- Migrations log will be visible within the GUI, so that users can
  track/view/compare model versions.
- Two-way ERD that allows users to change relational data that is then
  reflected onto their actual database
- Additional support for MySQL, SQL Server, etc.

## Documentation

More information on how to use DenoGres and leverage all its wonderful
abstraction functionality can be found here: https://denogres.deno.dev/

## Contributors

### Version 3.0

- Azal Adeel | [GitHub](https://github.com/azaladeel) |
  [LinkedIn](https://www.linkedin.com/in/azal-adeel/)
- Joe Hynan | [GitHub](https://github.com/JoeH1020) |
  [LinkedIn](https://www.linkedin.com/in/josephhynan/)
- James Howat | [GitHub](https://github.com/jbhowat) |
  [LinkedIn](https://www.linkedin.com/in/jamesbhowat/)
- Hao Ze Lin| [GitHub](https://github.com/LinHAO-1) |
  [LinkedIn](https://www.linkedin.com/in/linhaoze/)

### Version 2.0

- Anthony Lo | [GitHub](https://github.com/anthonylo87) |
  [LinkedIn](https://linkedin.com/in/87anthonylo/)
- Henry Park | [GitHub](https://github.com/CodeDenma) |
  [LinkedIn](https://linkedin.com/in/henrytpark/)
- Carlos Villarreal | [GitHub](https://github.com/Jiggyloww) |
  [LinkedIn](https://linkedin.com/in/carlosvillarrealsb)
- Eddie Wu | [GitHub](https://github.com/edi-wu) |
  [LinkedIn](https://linkedin.com/in/edi-wu)

### Version 1.0

- Ben Engelberg | [GitHub](https://github.com/bengelberg) |
  [LinkedIn](https://linkedin.com/in/benengelberg)
- Moonhee Hur | [GitHub](https://github.com/mhurcs) |
  [LinkedIn](https://linkedin.com/in/moonheehur)
- Tesia Hwang | [GitHub](https://github.com/tesiahwang) |
  [LinkedIn](https://linkedin.com/in/tesia-hwang)
- Kristen Lu | [GitHub](https://github.com/kristenlu24) |
  [LinkedIn](https://linkedin.com/in/kristen-lu)
- Allison Roderiques | [GitHub](https://github.com/allirod) |
  [LinkedIn](https://linkedin.com/in/allison-roderiques)

## License

MIT
