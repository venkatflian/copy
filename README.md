
#rail fence
pt = input("Enter the plain text: ")
key = int(input("Enter the key: "))
mat = [["*" for i in range(len(pt))] for j in range(key)]
row = 0
col = 0
flag = False
for i in range(len(pt)):
  if row == 0 or row==key-1:
    flag = not flag
  if flag == True:
    mat[row][col] = pt[i]
    row+=1
    col+=1
  else:
    mat[row][col] = pt[i]
    row-=1
    col+=1
en = ""
for i in range(key):
  for j in range(len(pt)):
    if mat[i][j] != "*":
      en+=mat[i][j]
print("Encrypted Message: ",en)

mat1 = [["*" for i in range(len(en))] for j in range(key)]
drow = 0
dcol = 0
flag1 = False
for i in range(len(en)):
  if drow == 0 or drow == key-1:
    flag1 = not flag1
  if flag1 == True:
    mat1[drow][dcol] = "#"
    drow+=1
    dcol+=1
  else:
    mat1[drow][dcol] = "#"
    drow-=1
    dcol+=1
index = 0
for i in range(key):
  for j in range(len(en)):
    if index<len(en) and mat1[i][j]=="#":
      mat1[i][j] = en[index]
      index+=1
d1 = 0
d2 = 0
f = False
d = ""
for i in range(len(en)):
  if d1 == 0 or d1 ==key-1:
    f = not f
  if f == True:
    d+=mat1[d1][d2]
    d1+=1
    d2+=1
  else:
    d+=mat1[d1][d2]
    d1-=1
    d2+=1
print("Decrypted Message: ",d)

#verman cipher

text=input("Enter the Text: ").upper()
key=input("Enter the key: ").upper()
if len(text)!=len(key):
  print("Invalid Key")
en=""
de=""
for i in range(len(text)):
  en+=chr(((ord(text[i])-65)%26^(ord(key[i])-65)%26)+65)
print("\nEncrypted: ",en)
for j in range(len(text)):
  de+=chr(((ord(en[j])-65)^((ord(key[j])))-65)%26+65)
print("Decrypted: ",de)

#RSA
p = 7
q = 13
m = 13
n =p*q
z=(p-1)*(q-1)
for i in range (2,z-1)
  e = i
  if math.gcd(e,z)==1
    print(f"e:{e}")
  break
d = pow(e,-1,z)
cipher = pow(m,e,n)
pt = pow(cipher,d,n)
print("cipher: ", cipher)
print("key: ",pt)


