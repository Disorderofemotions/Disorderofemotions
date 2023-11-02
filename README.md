import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;

public class DatabaseDeletion extends Application {

    @Override
    public void start(Stage primaryStage) {
        // Инициализация элементов GUI
        Button deleteButton = new Button("Удалить элемент из базы данных");

        // Обработчик нажатия на кнопку
        deleteButton.setOnAction(e -> {
            // Здесь должен быть код удаления элемента из базы данных
            // Например, вызов метода удаления или запрос к базе данных
            // Пример: database.deleteItem(itemId);
        });

        VBox root = new VBox(10);
        root.getChildren().addAll(deleteButton);

        Scene scene = new Scene(root, 300, 200);
        primaryStage.setTitle("Удаление из базы данных");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
 Дополните код:
Метод deleteItem() должен быть заменен соответствующим вызовом вашей базы данных для удаления элемента.
При нажатии на кнопку, вы можете передать идентификатор (или другую информацию) для удаления конкретного элемента из базы данных.
Подключение к базе данных:
Убедитесь, что у вас есть соединение с базой данных и методы для выполнения операций, таких как удаление элементов.
Это базовый пример для демонстрации создания кнопки удаления в интерфейсе. Не забудьте обеспечить безопасность и подтверждение удаления перед выполнением операции удаления элемента из базы данных.

Если у вас есть специфические требования или тип базы данных (например, SQL, NoSQL), нужно реализовать соответствующую логику удаления элементов из этой базы данных.


User


Save & Submit
