# Feature Workflow Guide

## 1) Generate a Design

On Studio page:

1. Enter API URL
2. Choose metal, category, weight, and style
3. Add optional design details
4. Click **Craft Your Masterpiece**

The app creates a detailed prompt and requests an image from backend.

## 2) Save to Favorites

After generation:

- Click **Save** to store the design in localStorage
- Saved design appears on `/favorites`

Favorites page supports:

- Download
- Remove
- Buy Now (opens booking form)

## 3) Book a Design

You can book from:

- Studio page (**Book Design**)
- Favorites page (**Buy Now**)

Required fields:

- Customer name
- Phone number
- Address

Optional fields:

- Advance payment
- Notes

On submit, order data is saved into ledger.

## 4) Ledger Management

Ledger page (`/ledger`) shows:

- Customer details
- Design attributes (category, metal, style, weight, details)
- Prompt text
- Saved design image

Actions:

- Click image to open preview modal
- Download image

## Data Persistence

All data is browser-local only:

- Favorites: `komal-jewellery-favorites`
- Ledger: `komal-jewellery-ledger`