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


public class Main extends Application {
	
	Button shapeButton;
	
    public static void main(String[] args) {
        Application.launch(args);
    }
    
    @Override
    public void start(Stage primaryStage) throws Exception {
        primaryStage.setTitle("");
        final Group root = new Group();
        Scene scene = new Scene(root, 1000, 500, Color.WHITE);
        
        shapeButton = new Button ();
        shapeButton.setText("New Shape here");
  
        
        scene.addEventHandler(MouseEvent.MOUSE_CLICKED, new EventHandler<MouseEvent>(){
        	public void handle (MouseEvent event){
        			
            		Rectangle r = new Rectangle(event.getSceneX(), event.getSceneY(), 30, 30);
                    r.setFill(Color.BLUE);
                    root.getChildren().addAll(r); 
        	}

        });
		
        
        Circle x = new Circle();
        x.setCenterX(50);
        x.setStrokeWidth(50);
        
       
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}
