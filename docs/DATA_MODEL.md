# SingleShelf Data Model (v2)

## User
- id
- email
- password_hash
- username
- display_name
- avatar_url (nullable)
- subscription_tier (free | monthly | annual | lifetime)
- subscription_status (active | cancelled | expired)
- stripe_customer_id (nullable)
- member_number (nullable — first 1,000 lifetime only)
- created_at
- last_login_at

## Game
- id
- igdb_id
- title
- cover_url
- summary
- platforms (array of strings)
- genres (array of strings)
- release_date
- developer
- publisher
- created_at
- updated_at

## UserGame (personal shelf)
- id
- user_id
- game_id
- status (backlog | playing | beaten | abandoned)
- completion_time_hours (nullable)
- notes (nullable — private user notes)
- added_at
- started_at (nullable)
- beaten_at (nullable)

## Rating
- id
- user_id
- game_id
- stars (1–5)
- created_at
- updated_at
- is_public (derived: true only if user has active paid subscription)

## Review
- id
- user_id
- game_id
- body
- created_at
- updated_at
- is_public (derived: true only if user has active paid subscription)

## WishlistItem
- id
- user_id
- game_id
- added_at
- priority (nullable)

## PriceAlert
- id
- user_id
- game_id
- target_price
- currency
- platform_preference (physical | digital | any)
- is_active
- created_at
- last_triggered_at (nullable)

## PriceRecord
- id
- game_id
- price
- currency
- store_name
- store_url (nullable)
- type (physical | digital)
- recorded_at

## PlaySession (for future minigames)
- id
- user_id
- game_type
- score
- played_at
- metadata (json)

## Forum structures (paid only — outline)
- ForumCategory (id, name, description, sort_order)
- ForumThread (id, category_id, user_id, title, created_at, is_locked)
- ForumPost (id, thread_id, user_id, body, created_at, updated_at)
