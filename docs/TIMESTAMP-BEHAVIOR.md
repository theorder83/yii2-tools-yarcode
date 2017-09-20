# TimestampBehavior

This class is inherited from the original timestampBehavior class and override attributes:
* createdAtAttribute - the default value is changed from `created_at` to `createdAt`
* updatedAtAttribute - the default value is changed from `updated_at` to `updatedAt`
* If the `value` parameter is not set, then the expression `NOW()` will be used, and not the function `time()`

## Usage
The use is no different from using the original behavior. But now everything works fine if the fields in the database have the `DATETIME` type.

```
yarcode\base\behaviors\TimestampBehavior;

public function behaviors()
{
    return [
        TimestampBehavior::className(),
    ];
}
```

Attention! The attribute will not hold the timestamp value, but the Expression object itself after the record has been saved. If you need the value from DB afterwards you should call the `refresh()` method of the record.