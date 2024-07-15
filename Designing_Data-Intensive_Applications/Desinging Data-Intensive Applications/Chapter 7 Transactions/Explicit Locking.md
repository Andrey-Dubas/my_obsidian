
```
BEGIN TRANSACTION

SELECT * FROM figures
WHERE name='robot' and game_id=222
FOR UPDATE

**WRITES**

COMMIT
```

