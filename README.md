```JS

const getRandomInt = (min, max) => {
  const rand = Math.random() * (max - min)
  return Math.floor(rand + min)
}

const buildFakeName = () => {
  const randomNumber = getRandomInt(0, 6)
  const names = ['Andre', 'Ricardo', 'Fiuza', 'Bruna', 'Thais', 'Ingrid']

  return names[randomNumber]
}

const buildFakeAge = () => {
  const randomNumber = getRandomInt(10, 70)

  return randomNumber
}

const buildFakeGender = () => {
  const randomNumber = getRandomInt(0, 3)
  const names = ['Male', 'Female', 'Other']

  return names[randomNumber]
}

const buildFakeCivilStatus = () => {
  const randomNumber = getRandomInt(0, 4)
  const names = ['Single', 'Married', 'Divorced', 'Widowed']

  return names[randomNumber]
}

const buildFakeChildren = () => {
  const randomNumber = getRandomInt(0, 10)

  return randomNumber
}

const buildFakeTeam = () => {
  const randomNumber = getRandomInt(0, 4)
  const names = ['Vasco da Gama', 'Flamengo', 'Botafogo', 'Fluminense']

  return names[randomNumber]
}

const generateRandomPerson = (total) => {
  const arr = []
  for (let i = 1; i <= total; i += 1) {
    arr.push({
      name: buildFakeName(),
      age: buildFakeAge(),
      gender: buildFakeGender(),
      civilStatus: buildFakeCivilStatus(),
      childrens: buildFakeChildren(),
      team: buildFakeTeam()
    })
  }

  return arr
}

// Generate random people
const peopleResearch = generateRandomPerson(30)

const getSingleFemalePerson = () => {
  const people = peopleResearch.filter((person) => person.civilStatus.toLowerCase().includes('single') && person.gender.toLowerCase().includes('female'))

 return people
}

const getMariedWomanWithChildrens = () => {
  const women = peopleResearch.filter((person) => person.gender.toLowerCase().includes('female'))

  const married = women.filter((woman) => woman.civilStatus.toLowerCase().includes('married'))

 return married.filter((m) => m.childrens > 3)
}

const getManThatLoveVasco = () => {
 const men = peopleResearch.filter((person) => person.gender.toLowerCase().includes('male'))

const result = men.filter((man) => man.team.toLowerCase().includes('vasco'))

return result
}

console.log('-------- all data --------', peopleResearch)

// Get single female person
console.log('Get single female person', getSingleFemalePerson())
// // Get married woman if more than 3 childrens
console.log('Get married woman if more than 3 childrens', getMariedWomanWithChildrens())
// Get mans that love Vasco da Gama
console.log('Get mans that love Vasco da Gama', getManThatLoveVasco())
// Get children that have children

```
