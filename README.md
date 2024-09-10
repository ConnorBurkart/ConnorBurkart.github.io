# Connor Burkart Code Examples!

## Unit Testing
JUnit testing is important because it catches bugs early, ensuring code reliability. It simplifies debugging by verifying components work correctly. Automated testing also boosts productivity and keeps the code stable.

``` java

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
```

## Moblie Applications with Flutter
[Video about our App](https://www.youtube.com/watch?v=g4dTerZpAcQ&list=LL&index=23&ab_channel=HaydenRoof)

Dart is the primary language used for building apps within the Flutter framework. It allows for fast development with a rich set of pre-built widgets and tools. Using Dart with Flutter enables smooth, high-performance mobile applications across multiple platforms, like Android and iOS, from a single codebase.

```java
    return CupertinoPageScaffold(
      child: Column(
        children: <Widget>[
          Text('CampusQuest'),
          Padding(
          padding: const EdgeInsets.all(16.0),
          child: ListView( // Using ListView to avoid overflow on smaller devices
            shrinkWrap: true,
            children: [
              SizedBox(
                height: MediaQuery.of(context).size.height * 0.3, // Adjust the size to 30% of the screen height
                child: Image.asset('assets/img/static-paw-003940-c_orange_1.jpg', fit: BoxFit.contain),
              ),
              CupertinoTextField(
                controller: _usernameController,
                placeholder: 'Username',
                style: const TextStyle(color: Colors.black),
              ),
              CupertinoTextField(
                controller: _passwordController,
                placeholder: 'Password',
                style: const TextStyle(color: Colors.black),
                obscureText: true,
              ),
              const SizedBox(height: 20),
              ElevatedButton(
                onPressed: _login,
                child: const Text('Sign in', style: TextStyle(color: Colors.black)),
                style: ButtonStyle(
                  backgroundColor: MaterialStateProperty.all(Colors.blue),
                ),
              ),
              const SizedBox(height: 20), 
              Center( // Wrap with Center to align to the middle
                child: GestureDetector(
                  onTap: () {
                    // Add your logic for "Forget password" here
                  },
                  child: const Text(
                    'Forget password?',
                    style: TextStyle(color: Colors.black, decoration: TextDecoration.underline),
```
## Fitts Law
This program simulates target selection tasks with varying sizes and distances. It measures the time taken and shows that smaller, farther targets take longer to hit. The results confirm Fitts' Law by illustrating the relationship between distance, size, and movement time.

![image](https://github.com/user-attachments/assets/8ecb75cf-aa7d-4f43-8392-c4ef3fc1920c)'

The data shows that smaller, farther targets take longer to click. For instance, Trial 1 took 919 ms for a 129-pixel target at 388 pixels away, while Trial 4 was faster with a larger, closer target. This is important for designing efficient user interfaces based on Fitts' Law.

![image](https://github.com/user-attachments/assets/172ba8c5-bb0b-43da-82f3-677eeeb8da1b)

## AVL Trees

An AVL tree is a self-balancing binary search tree that maintains a height difference of at most one between subtrees. This balancing ensures efficient 
𝑂(log𝑛)O(logn) operations for insertion, deletion, and lookup. AVL trees are important because they prevent performance degradation due to tree imbalance.
The insert function adds a value to the tree, creating left or right child nodes if needed, and recursively places the value in the correct subtree. After each insertion, it calls balanceTree() to maintain the AVL tree's balance.

``` c++
void OurCPSC3120Tree::insert( int val ){
  if( !getValue() ){
    setValue( val );
  }
  else if( val < getValue() && !getLeft() ){
    left = new OurCPSC3120Tree();
    getLeft()->setParent( *this );
    getLeft()->insert( val );
  }
  else if( val > getValue() && !getRight() ){
    right = new OurCPSC3120Tree();
    getRight()->setParent( *this );
    getRight()->insert( val );
  }
  else if( val < getValue() ){
    getLeft()->insert( val );
  }
  else{
    getRight()->insert( val );
  }

  balanceTree();
  
  return;
}
```

The balanceTree() function checks the height of the left and right subtrees to determine if the tree is unbalanced. It applies specific rotations (left, right, left-right, or right-left) based on the imbalance to restore balance. These rotations adjust the structure of the tree to maintain the AVL tree property, ensuring that the height difference between subtrees remains minimal.

``` c++
void OurCPSC3120Tree::balanceTree(){
  if( !getRight() && getLeft() && !getLeft()->getLeft() && getLeft()->getHeight() >= 2 ){
    rotateLeftRight();
    return;
  }
  if( !getRight() && getLeft() && getLeft()->getLeft() && getLeft()->getRight() && getLeft()->getRight()->getHeight() > getLeft()->getLeft()->getHeight() ){
    rotateLeftRight();
    return;
  }
  if( !getLeft() && getRight() && !getRight()->getRight() && getRight()->getHeight() >= 2 ){
    rotateRightLeft();
    return;
  }
  if( !getLeft() && getRight() && getRight()->getRight() && getRight()->getLeft() && getRight()->getLeft()->getHeight() > getRight()->getRight()->getHeight() ){
    rotateRightLeft();
    return;
  }
  if( !getLeft() && getRight() && getRight()->getHeight() >= 2 ){
    rotateLeft();
    return;
  }
  if( getLeft() && getRight() && getRight()->getHeight() >= ( getLeft()->getHeight() + 2 ) ){
    rotateLeft();
    return;
  }
  if( !getRight() && getLeft() && getLeft()->getHeight() >= 2 ){
    rotateRight();
    return;
  }
  if( getRight() && getLeft() && getLeft()->getHeight() >= ( getRight()->getHeight() + 2 ) ){
    rotateRight();
    return;
  }
}
```

### Hash Mapping



