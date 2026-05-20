# Mini-Project---Library-Management-System
class Book:
    def __init__(self, book_id, title, author):
        self.book_id = book_id
        self.title = title
        self.author = author
        self.available = True 


class Member:
    def __init__(self, member_id, name, email):
        self.member_id = member_id
        self.name = name
        self.email = email


class LibraryService:
    def __init__(self):
        
        self._books = {}
        self._members = {}

    def add_book(self):
     
        print("\n--- Add Book ---")
        
        book_id = input("Input: Book ID: ")
        title = input("Input: Book Title: ")
        author = input("Input: Book Author: ")
        
        new_book = Book(book_id, title, author)
        
        self._books[new_book.book_id] = new_book
        
        print(f"Output: \"Book added: {title}\"")

    def register_member(self):
  
        print("\n--- Register Member ---")
      
        member_id = input("Input: Member ID: ")
        name = input("Input: Member Name: ")
        email = input("Input: Member Email: ")
        
        new_member = Member(member_id, name, email)
        
        self._members[new_member.member_id] = new_member
        
        print(f"Output: \"Member registered: {name}\"")


def main():
   
    library_service = LibraryService()
    
    while True:
        print("\n===== LIBRARY MENU =====")
        print("1. Add Book")
        print("2. Register Member")
        print("3. Exit")
        
        choice = input("Enter choice: ")
        
        if choice == "1":
            library_service.add_book()
        elif choice == "2":
            library_service.register_member()
        elif choice == "3":
            print("Exiting application. Goodbye!")
            break
        else:
            print("Invalid choice, please select 1, 2, or 3.")


if __name__ == "__main__":
    main()
    