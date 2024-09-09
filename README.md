# Meet Connor!

# Code Examples 
## Unit Testing
Explanation here 

```java
@Test
    public void testSquareArea() {
        // Test case for area of a square (side^2)
        double sideLength = 5;
        double expectedArea = sideLength * sideLength;
        assertEquals(expectedArea, 25, "Square area calculation is incorrect");
    }

    @Test
    public void testTriangleHeight() {
        // Test case for height of a triangle (2 * area / base)
        double base = 10;
        double area = 30;
        double expectedHeight = (2 * area) / base;
        assertEquals(expectedHeight, 6, "Triangle height calculation is incorrect");
    }

    @Test
    public void testCircleCircumference() {
        // Test case for circumference of a circle (2 * π * radius)
        double radius = 7;
        double expectedCircumference = 2 * Math.PI * radius;
        assertEquals(expectedCircumference, 2 * Math.PI * 7, "Circle circumference calculation is incorrect");
    }
