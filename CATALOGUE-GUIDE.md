# Updating the M3 product catalogue

The public website reads product listings from `products.json`. Only people
with write access to the GitHub repository can change the catalogue or upload
photos. Changes are published to the public site after GitHub Pages finishes
building.

## Edit a product

1. Sign in to GitHub and open the
   [M3website repository](https://github.com/TaletheDEV/M3website).
2. Open `products.json` and choose **Edit this file**.
3. Update a product's details, or copy a product object to add another item.
4. Choose **Commit changes** to save. Keep valid JSON syntax: double quotes,
   commas between fields, and no comma after the final field.

Each product uses these fields:

```json
{
   "name": "Crocs",
  "category": "Category name",
  "description": "Short product description",
  "badge": "Optional short label",
  "price": "K45",
  "tone": "#e6ded2",
   "emoji": "🛍️",
   "image": "images/products/product-photo.jpg",
   "variants": [
      { "size": "39", "color": "Black", "quantity": 2 }
   ],
   "optionsPrompt": "Ask us about available sizes and colors."
}
```

`name`, `category`, and `description` are required. `badge`, `price`, `tone`,
`emoji`, `image`, `variants`, and `optionsPrompt` are optional. If no image is
supplied, the emoji is shown. The category filters on the site are created
automatically from the catalogue.

## Set available sizes, colors, and quantities

For Crocs and slides, add one `variants` entry for each size/color combination.
The quantity appears beside that combination on the product card:

```json
"variants": [
   { "size": "39", "color": "Black", "quantity": 2 },
   { "size": "40", "color": "White", "quantity": 1 }
]
```

For men's and women's perfumes, put the fragrance name or type and size in
`type`, then enter its available quantity:

```json
"variants": [
   { "type": "Fresh scent, 50ml", "quantity": 3 },
   { "type": "Woody scent, 100ml", "quantity": 1 }
]
```

Leave `variants` empty and add an `optionsPrompt` when current options or stock
have not been entered. The site will show the prompt so customers can contact
M3 to confirm availability.

## Add or replace a product photo

1. In the repository, choose **Add file → Upload files**.
2. Upload the photo to `images/products/` (create the folders if needed).
   Use a short filename with no spaces, such as `black-crocs.jpg`.
3. Commit the photo to the `main` branch.
4. Edit that product in `products.json` and set its `image` value to the exact
   path, for example `"images/products/black-crocs.jpg"`.
5. Commit the JSON change. The image path and filename are case-sensitive.

The repository and GitHub Pages site are public, so product details and photos
committed here will be visible to everyone. Repository write access controls
who can change them; never put passwords, private customer information, or
secret credentials in the repository.
