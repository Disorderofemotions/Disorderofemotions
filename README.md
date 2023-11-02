
xml
<Button
    android:id="@+id/deleteButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Удалить запись"
    android:onClick="deleteRecord" /
java
public class MainActivity extends AppCompatActivity {
    private SQLiteOpenHelper dbHelper;
    // Другие переменные и методы

    public void deleteRecord(View view) {
        SQLiteDatabase db = dbHelper.getWritableDatabase();
        // Здесь вы можете определить логику выбора записи для удаления, например, по ID.
    // Например, если у вас есть таблица "my_table" и поле "id" для уникальных идентификаторов:
    int recordIdToDelete = 1; // Здесь укажите нужный вам ID.
    String selection = "id=?";
    String[] selectionArgs = {String.valueOf(recordIdToDelete)};
    int rowsDeleted = db.delete("my_table", selection, selectionArgs);

    if (rowsDeleted > 0) {
        // Запись успешно удалена
        Toast.makeText(this, "Запись удалена", Toast.LENGTH_SHORT).show();
    } else {
        // Запись не найдена
        Toast.makeText(this, "Запись не найдена", Toast.LENGTH_SHORT).show();
    }
    
    db.close();
}
}

