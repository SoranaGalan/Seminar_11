# Seminar_11
# Revival after the holiday and preparing for the practical exam, year 1, semester 1


from domain import Team
from repository import TeamRepository

def printRepo(repo):
    print("Current repository is:")
    for elem in repo.getData():
        print(elem)

def delBelow100(repo):
    r = TeamRepository()
    for elem in repo.getData():
        if elem.getScore() >= 100:
            r.addTeam(elem)
    return r

def updateScore(repo):
    name = input("Update the score of the folllowing team:")
    for elem in repo.getData():
        if elem.getName() == name:
            try:
                newscore = int(input("Updated score:"))
                elem.setScore(newscore)
            except Exception as e:     
                print(e)
                return

def filterAbove100(repo):
    r = TeamRepository()
    for elem in repo.getData():
        if elem.getScore() < 100:
            r.addTeam(elem)
    return r
    
def sortDecreasing(repo):
    repo.getData().sort(key = lambda x: x.getScore(), reverse = True)

# verifications

t1 = Team("team1", 90)
t2 = Team("team2", 110)
t3 = Team("team", 85)

repo = TeamRepository()
repo.addTeam(t1)
repo.addTeam(t2)
repo.addTeam(t3)

#print("Function Add team:")
#printRepo(repo)

'''repo = delBelow100(repo)
printRepo(repo)'''

'''updateScore(repo)
printRepo(repo)'''

'''repo = filterAbove100(repo)
printRepo(repo)'''

sortDecreasing(repo)
printRepo(repo)

