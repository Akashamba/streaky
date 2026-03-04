### More ideas to think about

- Condensed view
- Batch operations
- Undo longer than 30s (maybe only current day)
- X times a week Frequency is an essential
- show month and day info like github
- “Streak freeze” token you can spend once per week
- haptics and animations for all interactions as appropriate. use https://haptics.lochie.me/ for haptics

### Targeted features

Iteration 1

- [x] view habits
- [x] Habit actions: create and delete habits (with confirmation modals)
- [x] make habit entries

Iteration 1.5

- [ ] encrypt access tokens
- [ ] optimize indexes
- [ ] reorder habits

Iteration 2:

- [ ] Habit settings menu (with card flipping animation)
- [ ] habit types/frequency
- [ ] Reorder habits
- [ ] Archive habits
- [ ] Batch features (batch complete, delete)
- [ ] Timezone support for using across multiple regions

Iteration 3:

- [ ] local first + offline access
- [ ] pwa
- [ ] web-push for notifications on pwa

Iteration 4:

- [ ] Social features: add friends, see their streaks, leaderboards, etc
- [ ] connect with notion to make journal entries about each completion

# Known Issues

- [ ] timezones (new day appears at 8 pm EDT (12 am UTC))
  - Store date in UTC, store timezone separately. Do all time calculations in UTC, convert for display only. FWIW Luxon is a great time/date library, used this in work for scheduling for an automated patching system.
- [ ] modal for delete
- [ ] optimistic update for create
- [ ] completion graph elements should not be selectable
- [ ] db push when there are tables already fails because of the sql expression column in the UNIQUE constraint of the habit_completions schema
  - Temp solution: manually drop the index on neon and then push the new schema, which will automatically add the schema
- [ ] update longest_streak correctly when undoing a completion, or leave it as append only field
