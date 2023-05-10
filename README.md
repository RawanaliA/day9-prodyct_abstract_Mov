# day9-prodyct_abstract_Mov
//first abstract class-product
public class Main {
    public static void main(String[] args) {
        Book b=new Book("rawan",80,"ali");
        b.getDiscount();
        Movie m=new Movie("ali",100,"bayan");
        m.getDiscount();   
    }
}
abstract class Product {
    private String name;
    private double price;

    public Product() {
    }

    public Product(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }
    abstract void getDiscount();
}
public class Movie extends Product {
    String director;

    public Movie(String name, double price, String director) {
        super(name, price);
        this.director = director;
    }

    public String getDirector() {
        return director;
    }

    public void setDirector(String director) {
        this.director = director;
    }

    @Override
    void getDiscount() {
        System.out.println("The price after discount is "+getPrice()*50/100);
    }
}
public class Book extends Product {
    String author;

    public Book() {

    }
    @Override
    void getDiscount() {

        System.out.println("The Book after discount is "+getPrice()*10/100);
    }

    public Book(String name, double price, String author) {
        super(name, price);
        this.author = author;
    }
    public String getAuthor() {
        return author;
    }
    public void setAuthor(String author) {
        this.author = author;
    }

}
<!--THE INTERFACE CLASS   -->
public class Main {
    public static void main(String[] args) {

        MovablePoint m=new MovablePoint(5,7,10,20);
        m.moveUp();
        m.Down();
        m.left();
        m.right();
    }
}
public interface Movable {
    void moveUp();
    void Down();
    void left();
    void right();
}
public class MovablePoint implements Movable {
    int x;
    int y;
    int speedX;
    int speedY;

    public MovablePoint(int x, int y, int speedX, int speedY) {
        this.x = x;
        this.y = y;
        this.speedX = speedX;
        this.speedY = speedY;
    }

    @Override
    public void moveUp() {
        y-=speedY;
        System.out.println("To move Up "+y);
    }

    @Override
    public void Down() {
        y+=speedY;
        System.out.println("To move down "+y);
    }
    @Override
    public void left() {

        x-=speedX;
        System.out.println("To move left "+x);
    }

    @Override
    public void right() {
        x+=speedX;
        System.out.println("To move Right "+x);
    }
}

