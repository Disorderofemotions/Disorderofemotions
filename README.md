Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                startActivity(intent);
            }
        });
    }
}
```

3. Создайте класс `SecondActivity`, который будет отображать второй экран:

```java
import android.database.Cursor;
import android.database.sqlite.SQLiteDatabase;
import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {
    private TextView todoTextView;
    private DatabaseHelper databaseHelper;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        todoTextView = findViewById(R.id.todoTextView);
        databaseHelper = new DatabaseHelper(this);
        SQLiteDatabase database = databaseHelper.getReadableDatabase();

        // Чтение записей из базы данных и отображение в TextView
        String query = "SELECT * FROM " + DatabaseHelper.TABLE_NAME;
        Cursor cursor = database.rawQuery(query, null);

        if (cursor.moveToFirst()) {
            StringBuilder stringBuilder = new StringBuilder();
            do {
                String title = cursor.getString(cursor.getColumnIndex(DatabaseHelper.COLUMN_TITLE));
                String date = cursor.getString(cursor.getColumnIndex(DatabaseHelper.COLUMN_DATE));
                String time = cursor.getString(cursor.getColumnIndex(DatabaseHelper.COLUMN_TIME));
                String description = cursor.getString(cursor.getColumnIndex(DatabaseHelper.COLUMN_DESCRIPTION));

                stringBuilder.append("Title: ").append(title).append("\n");
                stringBuilder.append("Date: ").append(date).append("\n");
                stringBuilder.append("Time: ").append(time).append("\n");
                stringBuilder.append("Description: ").append(description).append("\n\n");
            } while (cursor.moveToNext());

            todoTextView.setText(stringBuilder.toString());
        }

        cursor.close();
    }
}
```

Убедитесь, что у вас есть соответствующие макеты `activity_main.xml` и `activity_second.xml` для первого и второго экрана соответственно. Не забудьте также добавить разрешение для использования базы данных SQLite в вашем файле `AndroidManifest.xml`.

Я надеюсь, что этот код поможет вам начать разработку вашего приложения ежедневника! Если у вас возникнут дополнительные вопросы, не стесняйтесь спрашивать.
