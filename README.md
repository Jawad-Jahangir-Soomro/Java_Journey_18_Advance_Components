# Java Journey, 18: Advance Components.

Repository 18 focuses on advanced components of Java Swing such as JTable, JTree, JList, and JComboBox. These components allow developers to create interactive user interfaces for their applications and provide enhanced functionality for handling large amounts of data. Understanding how to use these components is essential for building robust and user-friendly Java applications.

## JTable

JTable is a Swing component used for displaying and editing data in tabular form. It allows users to view and edit tabular data and provides many features such as sorting, filtering, and cell editing. A JTable is created by defining a table model that contains the data to be displayed and a set of column names. Each row in the model represents a record, and each column represents a field in the record. The JTable is then created using this model and added to a Swing container. Here's an example:

```bash
String[] columnNames = {"Name", "Age", "Gender"};
Object[][] data = {
        {"John", 25, "Male"},
        {"Sarah", 30, "Female"},
        {"Tom", 40, "Male"},
        {"Kate", 35, "Female"}
    };
JTable table = new JTable(data, columnNames);
JScrollPane scrollPane = new JScrollPane(table);
```

In this example, we define a table with three columns: Name, Age, and Gender. We then create a data array containing four rows of data, each with a name, age, and gender. Finally, we create a JTable using the data and column names, and add it to a JScrollPane to enable scrolling. This table can then be added to a JPanel or other Swing container.

## JTree

JTree is a Swing component that displays hierarchical data structures such as a file system or a tree-like structure of objects. It provides a graphical representation of the parent-child relationship between nodes.

JTree is built using a tree model that defines the hierarchy of the data. Each node in the tree is represented by a tree node object, which contains the user object data and links to its parent and child nodes.

JTree supports various features like editing, drag and drop, and node selection. The tree can be customized with different icons, colors, and fonts for each node or level of nodes.

Example:

Below is an example of how to create a basic JTree with a root node and child nodes:

```bash
DefaultMutableTreeNode root = new DefaultMutableTreeNode("Root Node");

DefaultMutableTreeNode child1 = new DefaultMutableTreeNode("Child 1");
DefaultMutableTreeNode child2 = new DefaultMutableTreeNode("Child 2");
DefaultMutableTreeNode child3 = new DefaultMutableTreeNode("Child 3");

root.add(child1);
root.add(child2);
root.add(child3);

JTree tree = new JTree(root);
```

This code creates a JTree with a root node "Root Node" and three child nodes "Child 1", "Child 2", and "Child 3"

## JList

JList is a Swing component that provides a list of items to select from. It can be used to display a simple list of items or a list of more complex objects.

To create a JList, first, we need to create a list of items that we want to display. Then we create a JList object and pass the list of items to its constructor. We can customize the appearance of the JList by setting its background color, foreground color, selection color, and selection mode.

Example:

Suppose we want to create a JList of colors. We can create a list of colors as follows:

```bash
String[] colors = {"Red", "Green", "Blue", "Yellow"};
```

Then we create a JList object and pass the list of colors to its constructor:

```bash
JList<String> colorList = new JList<>(colors);
```

We can set the selection mode of the JList to allow multiple selections as follows:

```bash
colorList.setSelectionMode(ListSelectionModel.MULTIPLE_INTERVAL_SELECTION);
```

We can also customize the appearance of the JList by setting its background color, foreground color, and selection color:

```bash
colorList.setBackground(Color.WHITE);
colorList.setForeground(Color.BLACK);
colorList.setSelectionBackground(Color.YELLOW);
```

Finally, we can add the JList to a container, such as a JFrame, as follows:

```bash
JFrame frame = new JFrame();
frame.add(new JScrollPane(colorList));
frame.pack();
frame.setVisible(true);
```

This will create a JList of colors that can be displayed in a JFrame. The user can select one or more colors from the list.

## JComboBox

JComboBox is a Swing component that allows the user to select one item from a list of options. It consists of a drop-down list and an optional text field for filtering or editing the selection.

To create a JComboBox, we can use the following code:

```bash
String[] options = {"Option 1", "Option 2", "Option 3"};
JComboBox<String> comboBox = new JComboBox<>(options);
```

This creates a JComboBox with three options - Option 1, Option 2, and Option 3. We can add the JComboBox to a container such as a JFrame using the add() method.

We can also add an ActionListener to the JComboBox to perform some action when an item is selected. For example, we can display a message dialog with the selected item as follows:

```bash
comboBox.addActionListener(e -> {
    String selectedOption = (String) comboBox.getSelectedItem();
    JOptionPane.showMessageDialog(null, "You selected " + selectedOption);
});
```

This code adds an ActionListener to the JComboBox which displays a message dialog with the selected item whenever an item is selected.

JComboBox provides several methods to customize its appearance and behavior. For example, we can set the selected item using the setSelectedItem() method, or enable/disable the component using the setEnabled() method. We can also customize the rendering of the items in the list using a custom ListCellRenderer.
