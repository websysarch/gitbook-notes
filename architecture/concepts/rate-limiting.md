# Rate Limiting

The act of limiting the number of requests sent to or from a system. Rate limiting is most often used to limit the number of incoming requests in order to prevent DoS attack and can be enforced at the IP-address level, at the user-account level, or at the region level, for example, Rate limiting can also be implemented in tiers; for instance, a type of network request could be limited to 1 per sec,  5 per 10 sec and 10 per minute.

> Protects from clogging



### Implementation

* Use Key value pair for storage via `Redis`

### Types of Rate Limiting

#### Tier based&#x20;



### Node Implementation

This is for demonstration, In a real-world, rate-limiting is not implemented along with APP server, but instead before it (eg. in an API Gateway)

```javascript
const app = express()
const accesses = {} // In production, its Redis. Also, not part of the actual API
app.get('/some-path', (req, res) => {
    const {someUserKey} = req.headers
    const prevAccessTime = accesses[someUserKey]
    if(Date.now() - prevAccessTime < 5000) {
        res.status(429).send(`Too Many Requests`)
    }
    
    database.get('some-path', data => {
        accesses[someUserKey] = Date.now()
        res.send(data)
    })
})
```
