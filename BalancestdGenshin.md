n = int(input("How many time to calculate? : "))
list = []
CriList = []
CRI_MULT1 = 0
CRI_MULT2 = 0
Balance = 0
Balance2 = 0

for i in range(1,n+1) :
  print('')
  print("Set {}".format(i))
  ATK = int(input("TOTAL ATK : "))
  Cup = float(input("ELEMENTAL BONUS DAMAGE(%) : "))
  DMG_MULT = 1 + (Cup/100)
  CriRate = float(input("CRI RATE(%) : "))
  CriDamage = float(input("CRI DAMAGE(%) : "))
  CRI_MULT = 1 + ((CriRate/100)*(CriDamage/100))
  PreSkillAtk = ATK * DMG_MULT * CRI_MULT
  print("YOUR CRI MULT = {:.2f} , PRE SKILL ATK = {:.2f} ".format(CRI_MULT,PreSkillAtk))
  list.append(PreSkillAtk)
  CriList.append(CRI_MULT)

  if CRI_MULT1 == 0 :
    CRI_MULT1 = CRI_MULT
    CRI_MULT2 = i
  if CRI_MULT1 < CRI_MULT : 
    CRI_MULT1 = CRI_MULT
    CRI_MULT2 = i

  if Balance == 0 :
    Balance = PreSkillAtk
    Balance2 = i
  if Balance < PreSkillAtk :
    Balance = PreSkillAtk
    Balance2 = i

print('')
print("Best Cri Multiple Set is set {}".format(CRI_MULT2))
print("With Cri Multiple {:.2f}".format(max(CriList)))
print("Best Balance Status Set is set {}".format(Balance2))
print("With Balance Status {:.2f}".format(max(list)))
