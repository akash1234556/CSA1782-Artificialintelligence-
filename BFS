class Tree_struct:
   def __init__(self, data=None):
      self.key = data
      self.children = []

   def set_root(self, data):
      self.key = data

   def add_node(self, node):
      self.children.append(node)

   def search_node(self, key):
      if self.key == key:
         return self
      for child in self.children:
         temp = child.search_node(key)
         if temp is not None:
            return temp
      return None

   def bfs_operation(self):
      queue = [self]
      while queue != []:
         popped = queue.pop(0)
         for child in popped.children:
            queue.append(child)
         print(popped.key, end=' ')

my_instance = None

print('Menu (assume no duplicate keys)')
print('add <data> at root')
print('add <data> below <data>')
print('bfs')
print('quit')

while True:
   my_input = input('What operation would you do ? ').split()

   operation = my_input[0].strip().lower()
   if operation == 'add':
      data = int(my_input[1])
      new_node = Tree_struct(data)
      suboperation = my_input[2].strip().lower()
      if suboperation == 'at':
         my_instance = new_node
      elif suboperation == 'below':
         position = my_input[3].strip().lower()
         key = int(position)
         ref_node = None
         if my_instance is not None:
            ref_node = my_instance.search_node(key)
         if ref_node is None:
            print('No such key')
            continue
         ref_node.add_node(new_node)

   elif operation == 'bfs':
      if my_instance is None:
         print('The tree is empty')
      else:
         print('Breadth First Search traversal is : ', end='')
         my_instance.bfs_operation()
         print()

   elif operation == 'quit':
      break
