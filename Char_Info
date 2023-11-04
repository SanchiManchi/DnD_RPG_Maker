import random


class Rolls:
    def __init__(self):
        self.con = 0
        self.dex = 0
        self.wis = 0
        self.int = 0
        self.cha = 0
        self.str = 0

        self.abs_str = {"Athletics": 0}
        self.abs_dex = {"Acrobatics": 0, "Sleight of Hand": 0, "Stealth": 0}
        self.abs_int = {"Arcana": 0, "History": 0, "Investigation": 0, "Nature": 0, "Religion": 0}
        self.abs_wis = {"Animal Handling": 0, "Insight": 0, "Medicine": 0, "Perception": 0, "Survival": 0}
        self.abs_cha = {"Deception": 0, "Intimidation": 0, "Performance": 0, "Persuasion": 0}
        global Abs
        Abs = [self.abs_str, self.abs_dex, self.abs_int, self.abs_wis, self.abs_cha]


class Info:
    def __init__(self):
        self.race = ""
        self.clas = ""
        self.bkg = ""
        self.hp = 10
        self.vision = 30
        self.speed = 15
        self.traits = []


class Character(Rolls, Info):
    def __init__(self):
        Rolls.__init__(self)
        Info.__init__(self)
        self.con = random.randint(8, 18)
        self.dex = random.randint(8, 18)
        self.wis = random.randint(8, 18)
        self.int = random.randint(8, 18)
        self.cha = random.randint(8, 18)
        self.str = random.randint(8, 18)

    def create_char(self):
        print(f"Welcome to the world, new RPG character! "
              f"Your stats:\nStrength: {self.str}\nDexterity: {self.dex}"
              f"\nWisdom: {self.wis}\nIntelligence: {self.int}\n"
              f"Charisma: {self.cha}\nConstitution: {self.con}.\n"
              f"And of course, abilities:\n {Abs}")

    def race_bonus(self):
        match self.race:
            case "elf":
                self.int += 1
                self.dex += 2
                self.traits.extend(["Fey Ancestry", "Trance", "Keen Senses"])
            case "drow":
                self.cha += 2
                self.con -= 1
                self.dex += 2
                self.traits.extend(["Trance", "Charm Immunity", "Dark-vision"])
            case "human":
                self.int += 2
                self.cha += 2
                self.con -= 1
                self.traits.extend(["Diplomacy"])
            case "dragonborn":
                self.str += 2
                self.con += 1
                self.traits.extend(["Diplomacy", "Damage Res"])
            case "tiefling":
                self.cha -= 1
                self.str += 1
                self.con += 1
                self.traits.extend(["Dark-vision", "Hellish Res"])

    def class_bonus(self):
        match self.clas:
            case "bard":
                self.abs_cha["Performance"] += 1
                # Add function to add skill proficiencies.
                # SO it checks if it's a skill they can learn in their class
                # And if it's been added before
            case "rouge":
                self.abs_dex["Stealth"] += 1
