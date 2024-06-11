 DatePicker y ColorPicker

 demuestra el uso de los controles `DatePicker` y `ColorPicker`. La aplicación permite a los usuarios seleccionar una fecha y un color, y muestra los valores seleccionados tanto en la consola como en la interfaz de la aplicación.

## Características

- **DatePicker**: Permite al usuario seleccionar una fecha.
- **ColorPicker**: Permite al usuario seleccionar un color.
- **Botón Confirmar**: Imprime la fecha y el color seleccionados en la consola y los muestra en la interfaz de la aplicación.
  
#ilustracion
![image](https://github.com/Ivanmurillojr30/-DATEPICKER-Y-COLORPICKER/assets/168851753/cf5f243e-ac3d-4728-99cc-88b1268b46f7)

![image](https://github.com/Ivanmurillojr30/-DATEPICKER-Y-COLORPICKER/assets/168851753/c7ffb9cd-da7e-4d9e-b0e7-aae8af9bb692)


## Requisitos

- Kit de Desarrollo de Java (JDK) 17 o superior
- SDK de JavaFX

## Estructura del Proyecto
![image](https://github.com/Ivanmurillojr30/-DATEPICKER-Y-COLORPICKER/assets/168851753/ce3cac6b-d51e-4a20-ab8e-567808ed206f)

## Componentes Principales

### Main.java

Esta es la clase principal de la aplicación. Extiende `Application` y sobrescribe el método `start` para configurar la aplicación JavaFX.

- **DatePicker**: Un control que permite al usuario seleccionar una fecha.
- **ColorPicker**: Un control que permite al usuario seleccionar un color.
- **Botón ("Confirmar")**: Un botón que, al ser clicado, imprime la fecha y el color seleccionados en la consola y los muestra en la interfaz de la aplicación.
- **Etiquetas**: Usadas para etiquetar el `DatePicker` y el `ColorPicker`, y para mostrar los valores seleccionados.

### application.css

Este archivo se utiliza para estilizar la aplicación JavaFX. Se carga en la escena en el método `start` de `Main.java`.

## Ejecutar la Aplicación

1. Asegúrate de tener JDK 17 o superior y el SDK de JavaFX instalados.
2. Clona este repositorio en tu máquina local.
3. Abre el proyecto en tu IDE de Java preferido.
4. Asegúrate de que las bibliotecas de JavaFX estén configuradas correctamente en tu IDE.
5. Ejecuta la clase `Main.java`.

## Explicación del Código

### Main.java

```java
package application;

import java.time.LocalDate;
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.ColorPicker;
import javafx.scene.control.DatePicker;
import javafx.scene.control.Label;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.VBox;
import javafx.scene.paint.Color;
import javafx.stage.Stage;

public class Main extends Application {
    
    @Override
    public void start(Stage primaryStage) {
        try {
            // Crear controles
            DatePicker fechaPicker = new DatePicker();
            ColorPicker colorPicker = new ColorPicker();
            Button confirmarButton = new Button("Confirmar");

            // Crear etiquetas
            Label fechaLabel = new Label("Selecciona una fecha:");
            Label colorLabel = new Label("Selecciona un color:");
            Label titulo = new Label("Controles DatePicker y ColorPicker");

            // VBox para organizar los elementos
            VBox contenedor = new VBox();
            contenedor.setSpacing(10);
            contenedor.getChildren().addAll(titulo, fechaLabel, fechaPicker, colorLabel, colorPicker, confirmarButton);

            // Manejo del evento "clic" del botón
            confirmarButton.setOnAction(event -> {
                LocalDate fechaSeleccionada = fechaPicker.getValue();
                Color colorSeleccionado = colorPicker.getValue();

                // Mostrar selecciones en la consola
                System.out.println("Fecha seleccionada: " + fechaSeleccionada);
                System.out.println("Color seleccionado: " + colorSeleccionado);

                // Mostrar selecciones en otro componente de la interfaz (por ejemplo, un Label)
                Label resultadoLabel = new Label("Fecha: " + fechaSeleccionada + ", Color: " + colorSeleccionado);
                contenedor.getChildren().add(resultadoLabel);
            });

            // Crear y configurar la escena
            BorderPane root = new BorderPane(contenedor);
            Scene scene = new Scene(root, 400, 400);
            scene.getStylesheets().add(getClass().getResource("application.css").toExternalForm());
            
            // Configurar y mostrar el escenario principal
            primaryStage.setScene(scene);
            primaryStage.setTitle("Ejemplo JavaFX 17");
            primaryStage.show();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static void main(String[] args) {
        launch(args);
    }
}

# captura de pantallas
![image](https://github.com/Ivanmurillojr30/-DATEPICKER-Y-COLORPICKER/assets/168851753/a1ccf534-d69e-4076-9687-ed87e6478882)


