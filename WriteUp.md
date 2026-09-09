# Write-up

> This is the skeleton - replace everything in blockquotes with your own words
> and delete the prompts as you go. Aim for **~300 words** across the four
> questions; the route reference below can be as long as it needs to be.
>
> Write it like you're handing the work to a teammate. We'd rather read an
> honest "I ran out of time on X and here's what I'd do" than a polished list of
> accomplishments. **Submit this even if you didn't finish** - see CHALLENGE.md.

## 1. What did you build for Part B, and why that?

> I didn't have time to build something new for part B, I spend a lot of time trying to understand the full file structure, debugging the setup including docker issues and issues with tailwind.css.

## 2. What did you decide, and what did you rule out?

> My process was just breaking down the program as much as I could and this was the notes I took on a google document:
> App:
App loose:
Globals.css: includes global style that each page will use including a lgit coolor scheme and background and text color specifications
Layout.tsx: layout file
page.tsx: the homepage that acts as the server and calls getRestraunts() from lib/apiClient where export makes page’s function Homepage that gets and formats restaurant available to be used in other files
Api:
health/route.ts: just checks if server is running
restaurant/route.ts: defines get function which sends sql query to postgersql which is an instruction sent to the database to retrieve or change data and it specifically retrieves every column and puts newest restaurants first and .map formats and post is a method I must implement
Task: make post actually create a new restaurant, read restaurant fields, validate returning 400 if invalid otherwise insert into postgresql, convert database row and return status 201
id/route.ts: handles a single item, get end point uses query request to get restaurant with specific id but put and delete are not implemented
Task: read json body, validate restaurant data, update the restaurant whose id is params.id, return updated restaurant, return 404 if that ID does not exist and also fix delete by deleting from restaurants at the id and return 204 if it doesn’t exist
Db:
migrations/001_create_tables.sql: creates the the main tables necessary for feeding brennan
migrate.ts: locates migration directory, finds all sql files and gets all filenames in the migrations dir and sorts them alphabetically, loops through them alphabetically and executes it, then it sends entire sql file to postgresql and waits it to execute
pool.ts: creates a shared pg.pool which is a set of database connections from the database url and reuses it and this file just uses url or process.env to create a global pool to amke connection between next.js and postgresql efficient
seeds.ts: resets data with a standard test data that is consistent
Lib: shared code used by both frontend and api
types.ts: interfaces, converts postgers row into contract shape


## 3. Where did you cut corners?

> I still need to fix the created at timestamp, because when it prints it is always undefined.

---

## Part B: routes- I did not get to part B
```

## Known issues / what I'd do next

> I was honestly very caught off guard with this project, i haven’t worked with type script and while robotics and my internship with Dr. Chen involved connecting an API to frontend, but I didn’t need to work with that in robotics and it has been a while since my internship. So first I just had to understand what was happening. 
I didn't understand, but I just researched and use AI to help me understand all components of the project. Then I worked on the set up and had to debug an issue regarding failed import of tailwind.css which I somehow fixed during office hours. I would like to further understand the specifics, fix the issue with the undefined created at timestamps and implement my own feature for part B hopefully with less AI assistance. I tried my best to get as much done before the deadline.
