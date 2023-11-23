Для изменения цвета оформления приложения при нажатии на checkbox в Android Studio, вы можете использовать следующий подход:

1. В файле `res/values/styles.xml` определите два стиля для вашего приложения, например:

```xml
<style name="AppTheme.Light" parent="Theme.AppCompat.Light">
    <!-- Установите цветовые атрибуты для светлой темы -->
    ...
</style>

<style name="AppTheme.Dark" parent="Theme.AppCompat">
    <!-- Установите цветовые атрибуты для темной темы -->
    ...
</style>
```

2. В файле макета (`res/layout/activity_main.xml`) добавьте `CheckBox` и присвойте ему уникальный идентификатор:

```xml
<CheckBox
    android:id="@+id/themeCheckbox"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Изменить тему" />
```

3. В активности (`MainActivity.java`) найдите этот `CheckBox` по его идентификатору и установите слушатель событий:

```java
public class MainActivity extends AppCompatActivity {
    private CheckBox themeCheckbox;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        themeCheckbox = findViewById(R.id.themeCheckbox);
        themeCheckbox.setOnCheckedChangeListener(new CompoundButton.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(CompoundButton buttonView, boolean isChecked) {
                // Измените тему при изменении состояния checkbox
                if (isChecked) {
                    setTheme(R.style.AppTheme.Dark);
                } else {
                    setTheme(R.style.AppTheme.Light);
                }

                // Пересоздайте активность, чтобы изменения применились
                recreate();
            }
        });
    }
}
```

4. После пересоздания активности, новая тема будет применена.

Обратите внимание, что вы должны включить в файл манифеста (`AndroidManifest.xml`) атрибут `android:theme` с ссылкой на одну из стилей, чтобы установить начальную тему для приложения:

```xml
<application
    android:theme="@style/AppTheme.Light">
    ...
</application>
```

Теперь, при нажатии на `CheckBox`, цвет оформления приложения будет изменяться между светлой и темной темами.
