# SingleShelf Data Model (v1)

## User
- id
- email
- password_hash
- username
- subscription_tier (free | monthly | annual | lifetime)
- subscription_status
- created_at
- member_number (for first 1,000 lifetime only)

## Game
- id
- igdb_id (external reference)
- title
- cover_url
- platforms (array)
- genres (array)
- release_date
- description

## UserGame (personal shelf entry)
- id
- user_id
- game_id
- status (backlog | playing | beaten | abandoned)
- completion_time_hours (nullable)
- added_at
- beaten_at (nullable)

## Rating
- id
- user_id
- game_id
- stars (1–5)
- created_at
- is_public (true only if user is paid)

## Review
- id
- user_id
- game_id
- body (text)
- created_at
- is_public (true only if user is paid)

## Wishlist
- id
- user_id
- game_id
- added_at

## PriceAlert
- id
- user_id
- game_id
- target_price
- platform (physical | digital | any)
- created_at
- is_active

## PriceHistory
- id
- game_id
- price
- currency
- store
- type (physical | digital)
- recorded_at

## Forum (paid only)
- Category
- Thread
- Post
(basic structure to be detailed later)
