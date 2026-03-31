# Table-driven agent
agent_table = {
    ('Dirty', 'A'): 'Suck',
    ('Dirty', 'B'): 'Suck',
    ('Clean', 'A'): 'MoveRight',
    ('Clean', 'B'): 'MoveLeft'
}

class VacuumCleaner:
    def __init__(self, location='A', room_status=None):
        if room_status is None:
            room_status = {'A': 'Dirty', 'B': 'Dirty'}
        self.location = location
        self.room_status = room_status

    def perceive(self):
        return (self.room_status[self.location], self.location)

    def act(self, action):
        if action == 'Suck':
            self.room_status[self.location] = 'Clean'
        elif action == 'MoveRight':
            self.location = 'B'
        elif action == 'MoveLeft':
            self.location = 'A'

    def get_cleaning_percentage(self):
        total = len(self.room_status)
        clean = sum(1 for s in self.room_status.values() if s == 'Clean')
        return (clean / total) * 100

    def get_overall_status(self):
        if self.get_cleaning_percentage() == 100:
            return "The entire floor is CLEAN"
        else:
            return "The floor is not yet clean"

def table_driven_agent(percept):
    return agent_table.get(percept, 'NoOp')

# Main
vacuum = VacuumCleaner()

for step in range(4):
    percept = vacuum.perceive()
    action = table_driven_agent(percept)
    print(f"Step {step+1}: Percept {percept}, Action {action}")
    vacuum.act(action)
    print("Room Status:", vacuum.room_status)
    print("Cleaning Percentage:", vacuum.get_cleaning_percentage())
    print("Overall Status:", vacuum.get_overall_status())
    print("-" * 40)
