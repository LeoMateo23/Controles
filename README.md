import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.BorderPane;
import javafx.stage.Stage;

public class MenuApp extends Application {

    @Override
    public void start(Stage primaryStage) {
        // Creating the main menu bar
        MenuBar menuBar = new MenuBar();

        // Creating menus
        Menu fileMenu = new Menu("Archivo");
        Menu editMenu = new Menu("Editar");
        Menu helpMenu = new Menu("Ayuda");

        // Creating menu items for "Archivo" menu
        MenuItem newFile = new MenuItem("Nuevo");
        MenuItem openFile = new MenuItem("Abrir");
        MenuItem saveFile = new MenuItem("Guardar");
        MenuItem exitApp = new MenuItem("Salir");

        // Adding actions to menu items
        newFile.setOnAction(e -> System.out.println("Nuevo archivo seleccionado"));
        openFile.setOnAction(e -> System.out.println("Abrir archivo seleccionado"));
        saveFile.setOnAction(e -> System.out.println("Guardar archivo seleccionado"));
        exitApp.setOnAction(e -> System.out.println("Salir seleccionado"));

        // Adding menu items to "Archivo" menu with a separator
        fileMenu.getItems().addAll(newFile, openFile, saveFile, new SeparatorMenuItem(), exitApp);

        // Creating menu items for "Editar" menu
        MenuItem cut = new MenuItem("Cortar");
        MenuItem copy = new MenuItem("Copiar");
        MenuItem paste = new MenuItem("Pegar");

        // Adding actions to menu items
        cut.setOnAction(e -> System.out.println("Cortar seleccionado"));
        copy.setOnAction(e -> System.out.println("Copiar seleccionado"));
        paste.setOnAction(e -> System.out.println("Pegar seleccionado"));

        // Adding menu items to "Editar" menu with a separator
        editMenu.getItems().addAll(cut, copy, paste);

        // Creating menu items for "Ayuda" menu
        MenuItem about = new MenuItem("Acerca de");

        // Adding actions to menu items
        about.setOnAction(e -> System.out.println("Acerca de seleccionado"));

        // Adding menu items to "Ayuda" menu
        helpMenu.getItems().addAll(about);

        // Adding menus to the menu bar
        menuBar.getMenus().addAll(fileMenu, editMenu, helpMenu);

        // Creating a BorderPane and setting the menu bar at the top
        BorderPane root = new BorderPane();
        root.setTop(menuBar);

        // Creating the scene and setting the stage
        Scene scene = new Scene(root, 800, 600);
        primaryStage.setTitle("Menu Application");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
