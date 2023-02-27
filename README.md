## Generate a web gallery for your books.

My use case is to list all the books I want to give away.
This way friends can pick books they want before I throw them out.

Makes use of [Calibre](https://calibre-ebook.com)
- Generate a book entry (metadata and cover iamge) from only a ISBN nummer
- holds the actual book collection data

My workflow
1. Use an isbn scanner app to bulk scan the books (I use the (free) [Delicious Scanner app](https://apps.apple.com/app/id637919291) for iOS)
2. Copy the isbn list to Calibre > Add books > Add from ISBN
3. Edit metadata if needed
4. Export books as XML in Calibre > Convert books > Crearte a catalog of your books in calibre > Catalog format:XML; Catalog title: "books"  
   Alternatively, you can use the [calibredb](https://manual.calibre-ebook.com/generated/en/calibredb.html#catalog) cli tools to do so: For mac run `/Applications/calibre.app/Contents/MacOS/calibredb catalog books.xml`
5. Copy the resulting books.xml file this projects root folder
6. run `python3 run.py`

Then open ´dist/index.html´ in your browser to view the generated HTML page.


## Optional: Deploy to netlify

### Setup
- Copy `netlify.toml.example` to `netlify.toml`and change the build command so it works on your system.
- Run `netlify sites:create`
 

### Build and deploy 

`netlify deploy --build --prod`
