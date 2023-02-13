**Deprem Analiz**

```python
def fetch():
    url = 'https://api.orhanaydogdu.com.tr/deprem/kandilli/live'
    response = requests.get(url)
    return response.json()
    data = fetch()['result']

eqs = []

for eq in data:
    dummy = earthquake(eq['mag'], eq['depth'], eq['lokasyon'], eq['date'])
    eqs.append(dummy)

x = []
y = []

for eq in eqs:
    x.append(eq.getMagnitude())
    y.append(eq.getDepth())

ax.plot(x, y, 'ro')
```
