# Supabase Commands

## Local Setup
- `supabase init`: Initialize a new project.
- `supabase start`: Start local Supabase stack.
- `supabase stop`: Stop local Supabase stack.

## Database Schema
- Create a table:
  ```sql
  CREATE TABLE ai_tools (
    id UUID PRIMARY KEY,
    name TEXT NOT NULL,
    description TEXT,
    category TEXT NOT NULL
  );
