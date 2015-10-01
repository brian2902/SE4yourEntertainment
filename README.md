package application;
	
import javafx.event.ActionEvent;
import javafx.application.Application;
import javafx.event.EventHandler;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.input.MouseEvent;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;
import javafx.scene.layout.StackPane;


public class Main extends Application {
	
	Button rectButton;
	Button circleButton;
	
    public static void main(String[] args) {
        Application.launch(args);
    }
    
    @Override
    public void start(Stage primaryStage) throws Exception {
        primaryStage.setTitle("");
     	final StackPane root = new StackPane();
        Scene scene = new Scene(root, 1000, 500, Color.WHITE);
        
        rectButton = new Button ();
        rectButton.setText("New Rectangle");
        
        circleButton = new Button();
        circleButton.setText("New Circle");
        
  
        
        rectButton.setOnAction(new EventHandler<ActionEvent>(){
        	public void handle (ActionEvent event){	
        			root.getChildren().remove(0);
            		Rectangle r = new Rectangle(60, 30);
                    r.setFill(Color.BLUE); 
                    root.getChildren().add(r);
        	}

        });
        
        
        		
        
       
		rectButton.setLayoutX(200);
		rectButton.setLayoutY(200);
		circleButton.setLayoutX(100);
		circleButton.setLayoutY(100);
        root.getChildren().addAll(rectButton); 
 
        
       
        primaryStage.setScene(scene);
        primaryStage.show();
    }
