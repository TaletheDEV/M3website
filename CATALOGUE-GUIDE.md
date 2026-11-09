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
  "name": "Product name",
  "category": "Category name",
  "description": "Short product description",
  "badge": "Optional short label",
  "price": "K45",
  "tone": "#e6ded2",
  "emoji": "🛍️",
  "image": "images/products/product-photo.jpg"
}
```

`name`, `category`, and `description` are required. `badge`, `price`, `tone`,
`emoji`, and `image` are optional. If no image is supplied, the emoji is shown.
The category filters on the site are created automatically from the catalogue.

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
