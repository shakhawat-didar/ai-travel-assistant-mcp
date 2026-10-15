# Sample travel request

Plan a 3-day mid-range trip to Sajek Valley for two people. I prefer a comfortable hotel, local food, and scenic viewpoints. My user_id is demo-user-001.

## What to verify during the run

- The assistant calls `get_preference` first when `user_id` is available.
- Weather and place details come from tools, not unsupported guesses.
- If the user shares a new long-term preference, the assistant calls `save_preference`.
- The assistant does not claim live exchange rates while that tool is disabled.
- The final itinerary makes availability and booking limitations clear.
