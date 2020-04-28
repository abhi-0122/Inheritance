# Inheritance


class Person:
	def __init__(self, firstName, lastName, idNumber):
		self.firstName = firstName
		self.lastName = lastName
		self.idNumber = idNumber
	def printPerson(self):
		print("Name:", self.lastName + ",", self.firstName)
		print("ID:", self.idNumber)

class Student(Person):
  
    def __init__(self,firstName, lastName,id, scores):
        super().__init__(firstName,lastName,id)
        self.scores = scores
    
    def calculate(self):
        avg = sum(scores)/len(scores)
        if avg>=40 and avg<55:
            return 'D'
        if avg>=55 and avg<70:
            return 'P'
        return {0:'T',
        1:'T',
        2:'T',
        3:'T',
        7:'A',
        8:'E',
        9:'O',
        10:'O'
        }[avg//10]
    

  

line = input().split()
firstName = line[0]
lastName = line[1]
idNum = line[2]
numScores = int(input()) # not needed for Python
scores = list( map(int, input().split()) )
s = Student(firstName, lastName, idNum, scores)
s.printPerson()
print("Grade:", s.calculate())
