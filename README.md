# ZARA Clone – E‑commerce Frontend

A responsive ZARA‑style e‑commerce frontend built with **HTML**, **CSS**, and **vanilla JavaScript**.  
The app covers the full flow from browsing products to placing an order and seeing a dynamic confirmation page.

---

## Features

- ZARA‑inspired layout and navigation (WOMAN, MAN, KIDS, BEAUTY, SHOES, BAGS, PERFUMES).
- Shopping bag (cart) with add/remove/update quantity.
- Cart persistence using `localStorage`.
- Checkout with:
  - Shipping details form (name, email, phone, address, city, state, ZIP, country).
  - Multiple payment methods:
    - **Card** – brand detection (Visa, MasterCard, etc.) and length validation.
    - **UPI** – only lowercase letters and digits allowed around `@` (e.g. `name123@bank`).
    - **Cash on Delivery** – generates a random COD code.
- Custom modal alert component:
  - Replaces native `alert()`.
  - Red cross icon for errors/notices.
  - Green tick icon for successful order placement.
- Thank‑you page:
  - Reads order data from `localStorage`.
  - Shows generated order number.
  - Displays customer info, address, items, and total.

---

## Tech Stack

- **HTML5** – page structure and templates  
- **CSS3** – layout, responsive design, custom modal & typography  
- **JavaScript (ES6)** – DOM logic, validation, cart, alerts, `localStorage`  
- **Icons** – Font Awesome, Icons8

---

## Project Structure
├── index.html # Home page
├── woman.html # Category pages (similar: man, kids, etc.)
├── man.html
├── kids.html
├── beauty.html
├── shoes.html
├── bags.html
├── perfumes.html
├── cart.html # Shopping bag
├── checkout.html # Checkout + payment methods
├── thankyou.html # Order confirmation
├── help.html # Help / FAQ
├── payments.html # Payment methods information
├── pricingpolicy.html # Pricing policy page
├── cookies.html # Cookies policy
├── contact.html # Contact form
├── styles.css # Global styles
└── script.js # Cart, validation, custom alerts, etc.


---

## Key Implementation Details

### Cart & Local Storage

- Cart items are stored in `localStorage` so the bag persists between page loads.
- Helper functions like `getCart()` and `saveCart([])` handle reading and writing.

### Checkout Validation

- **Name** – letters and spaces only, minimum 2 characters.  
- **Email** – normalized to lowercase before validation.  
- **Phone** – exactly 10 digits.  
- **State** – must match a predefined list of Indian states/UTs.  
- **ZIP** – `123 456` format.  
- **Card** – brand inferred from BIN; length checked against brand rules.  
- **UPI** – regex `^[a-z0-9]{3,50}@[a-z0-9]{2,20}$` after converting input to lowercase.

### Custom Alert Modal

- A reusable function `showCustomAlert(title, message, type, callback)`:
  - `type: "error"` → red cross icon (validation messages, notices).
  - `type: "success"` → green tick icon (order placed, etc.).
- `showError(message)` wraps `showCustomAlert` for convenience.

---

## Order Flow

1. User adds items to cart from listing pages.  
2. On **cart.html**, user reviews items and proceeds to checkout.  
3. On **checkout.html**, user:
   - Fills shipping details.
   - Chooses payment method (Card / UPI / COD).
   - Passes all validations.
4. On successful validation:
   - An order data object is saved to `localStorage` as `checkoutOrder`.
   - A success modal with a green tick is shown.
   - User is redirected to **thankyou.html**.
5. On **thankyou.html**:
   - `checkoutOrder` is read from `localStorage`.
   - A random alphanumeric order number is generated.
   - Customer info, address, items, and total are rendered.

---

## Getting Started

### 1. Clone the repository

git clone https://github.com/your-username/zara-clone.git
cd zara-clone


### 2. Open in a browser

- Option A: Just open `index.html` with Live Server (VS Code) or directly in the browser.  
- Option B: Serve with a simple static server (recommended):

npx serve .


Then open the URL shown in the terminal.

---

## Future Improvements

- Hook up to a real backend / API.  
- Add authentication and order history.  
- Replace hard‑coded product data with dynamic JSON or API calls.  
- Add automated tests for validation and cart logic.

---

## Disclaimer

This project is an educational, non‑commercial clone inspired by ZARA’s design.  
All trademarks, brand names, and logos belong to their respective owners.

---

## Project SC<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 08 00 AM" src="https://github.com/user-attachments/assets/bc77b8c7-86e3-423d-ac55-288fa3599791" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 11 09 AM" src="https://github.com/user-attachments/assets/e083a4e5-f90a-434a-b6b1-25b22a5e2585" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 11 16 AM" src="https://github.com/user-attachments/assets/cdf8957a-3d2e-4ece-87c8-c01e7edf959b" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 12 22 AM" src="https://github.com/user-attachments/assets/01772868-2658-478e-8d77-75c10a828e29" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 12 31 AM" src="https://github.com/user-attachments/assets/f64517a7-b9e7-4a1e-9af0-628ba5df4e22" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 12 40 AM" src="https://github.com/user-attachments/assets/523c6660-3193-4df7-acc7-0a140d459d3a" />
<img width="1269" height="302" alt="Screenshot 2025-12-17 at 11 14 34 AM" src="https://github.com/user-attachments/assets/32739595-903c-445a-b2e5-76f3be4925e9" />
<img width="529" height="381" alt="Screenshot 2025-12-17 at 11 14 49 AM" src="https://github.com/user-attachments/assets/545bb6f5-0d31-411b-ba2b-767d0eaba610" />
<img width="517" height="325" alt="Screenshot 2025-12-17 at 11 15 07 AM" src="https://github.com/user-attachments/assets/a66271e3-36ed-4a76-9820-701c13aca1aa" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 17 34 AM" src="https://github.com/user-attachments/assets/2c59627e-d3b3-402b-b5a5-a7711d6dcb9c" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 18 54 AM" src="https://github.com/user-attachments/assets/4a8dfb9d-160f-4e30-bf18-22d7374fc5c1" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 20 01 AM" src="https://github.com/user-attachments/assets/1553189a-64c5-457d-90b4-423de911bdb6" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 21 16 AM" src="https://github.com/user-attachments/assets/143497a8-629e-47ea-a758-d34cb9649da7" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 22 04 AM" src="https://github.com/user-attachments/assets/3ecc14cd-968d-4795-89e2-0b52a0dc1ab2" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 22 44 AM" src="https://github.com/user-attachments/assets/5f940b7c-918c-44ba-84d6-881bb3599bb9" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 23 12 AM" src="https://github.com/user-attachments/assets/a0fe1bd8-5b83-4dad-877c-ecaec04a7c21" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 24 06 AM" src="https://github.com/user-attachments/assets/4c10e9c8-8b6b-48ee-874e-c3cf64a303c9" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 24 36 AM" src="https://github.com/user-attachments/assets/b2b27995-7b78-49a8-90c1-ce29f0d6a11a" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 24 56 AM" src="https://github.com/user-attachments/assets/200b798b-a128-4905-90e2-8fd772988e62" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 25 30 AM" src="https://github.com/user-attachments/assets/32c11eb4-a4de-4f09-b3e7-f96ef70b7c20" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 26 12 AM" src="https://github.com/user-attachments/assets/4a63558f-b542-4ef0-9b60-b9be6ba44842" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 26 57 AM" src="https://github.com/user-attachments/assets/c3234405-e261-4dcd-a1d7-e33893e7020e" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 28 06 AM" src="https://github.com/user-attachments/assets/2f727172-90b5-47cd-a92c-05e167263b95" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 28 09 AM" src="https://github.com/user-attachments/assets/9599f7fc-43a3-40f4-bac0-9f078ee785dd" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 28 51 AM" src="https://github.com/user-attachments/assets/1ddf1406-8cf7-4e44-ac2e-ed4b47300b5c" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 29 38 AM" src="https://github.com/user-attachments/assets/8ca5ac15-5b2c-4c8b-a0c2-37d8be0e4810" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 30 07 AM" src="https://github.com/user-attachments/assets/a6c17efc-996d-4dda-a205-60cdb4037b9f" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 31 00 AM" src="https://github.com/user-attachments/assets/6808eb67-1027-4c19-9cba-bc8f6dcff621" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 31 31 AM" src="https://github.com/user-attachments/assets/0e4e1021-6d1c-412d-9b75-243f985a1a15" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 31 55 AM" src="https://github.com/user-attachments/assets/8a9f6d89-d25c-40bf-a4e1-24dc314db722" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 32 32 AM" src="https://github.com/user-attachments/assets/d7719ee0-455e-4d7f-a807-7becc4400ba0" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 32 53 AM" src="https://github.com/user-attachments/assets/2c5f5fd4-d735-41e5-bc8d-f0c70d594658" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 33 16 AM" src="https://github.com/user-attachments/assets/40cfd463-3fee-4e7d-a852-2501bb527eb9" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 33 41 AM" src="https://github.com/user-attachments/assets/be8ed473-4929-4e15-ab5a-29c1a31bd68b" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 34 11 AM" src="https://github.com/user-attachments/assets/e1849224-22da-4d23-a282-8b5ffd245e00" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 34 18 AM" src="https://github.com/user-attachments/assets/d2ca1152-7c99-4404-9d15-fdc75d181510" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 34 24 AM" src="https://github.com/user-attachments/assets/9bd9724a-3159-4e3b-8726-4fe77f19a8e4" />
<img width="1280" height="800" alt="Screenshot 2025-12-17 at 11 35 53 AM" src="https://github.com/user-attachments/assets/284ce64f-66ab-4980-a41f-359068e04859" />
REEN SHORTS


