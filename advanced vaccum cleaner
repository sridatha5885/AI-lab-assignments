# Rooms: 1 = Dirty, 0 = Clean
rooms = {
    "Kitchen":   [1, 0, 1, 0],
    "Hall":      [0, 1, 1, 0],
    "Bedroom":   [0, 0, 0, 0],
    "SideRoom":  [0, 0, 0, 0]
}

positions = {
    0: "Left",
    1: "Centre Left",
    2: "Centre Right",
    3: "Right"
}

performance = 0
total_cells = 0

for room in rooms.values():
    total_cells += len(room)

def vacuum_agent(room_name, room):
    global performance
    print(f"\nEntering {room_name}")
    for i in range(len(room)):
        print(f"Moving to {positions[i]} position")
        if room[i] == 1:
            print("Dirt found → Suck")
            room[i] = 0
            performance += 1
        else:
            print("Clean → Move")

def room_status(room):
    clean = room.count(0)
    dirty = room.count(1)
    clean_percent = (clean / len(room)) * 100
    dirty_percent = (dirty / len(room)) * 100
    return clean_percent, dirty_percent

print("INITIAL STATUS")
for name, room in rooms.items():
    clean, dirty = room_status(room)
    print(f"{name}: {room} | Clean: {clean}% Dirty: {dirty}%")

for name, room in rooms.items():
    vacuum_agent(name, room)

print("\nFINAL STATUS")
for name, room in rooms.items():
    clean, dirty = room_status(room)
    print(f"{name}: {room} | Clean: {clean}% Dirty: {dirty}%")

performance_percent = (performance / total_cells) * 100
print("\nOverall Performance:", performance_percent, "%")
