# Lexical Density

Using Express API that takes sentences and returns the lexical density in json format. Lexical density is defined by the number of lexical words divided by the total number of words.

eg. Kat loves going <span style="color:red">to the</span> movies

returns:

```
{ "data":
    {
      overall_density: 0.42
    }
}
```

Multiple sentences can return overall and individual densities eg.

```
{
  "data": {
    sentence_density: [ 0.23, 0.1, 1.0, 0.0 ],
    overall_density: 0.42
  }
}
```

---

#### Installation

`git clone https://github.com/LondonJim/Lexical-Density-Express-API`

`npm install`

---

#### Start server

`npm start`


Besides the mocha/chai tests below I also use Postman API Development Environment

---

#### Routes

###### Overall density
```
POST /complexity
```
example post body json:
```
{
  "sentences" : "Jimmy loves going to the movies"
}
```
returns:
```
{
  "data": {
    overall_density: 0.42
  }
}
```

###### Sentence density breakdown
```
POST /complexity?mode=verbose
```

example post body json:
```
{
  "sentences" : "Kat likes going to the cinema. Jimmy enjoys listening to music."
}
```
returns:
```
{
  "data": {
    "sentence_density": [ 0.67, 0.8 ],
    "overall_density": 0.73
  }
}
```

---

#### Testing

Using Mocha and Chai libraries

`npm test`
