---
marp: true
author: De Wet Blomerus
size: 16:9
theme: default
---

<style>
  :root {
    color: black;
    background: white;
  }

  h1, h2, h3 {
    font-weight: 300;
    color: black;
  }

  a {
    color: black
    font-weight: 200;
  }

  h1 {
    text-align: center;
    font-size: 60px;
  }

  h2 {
    font-size: 40px;
  }

  pre, code {
    background-color: white;
    color: black;
  }

</style>

![bg](images/template-001.jpeg)

# Building a Globally Distributed Router in Elixir

---

![bg](images/template-001.jpeg)

## Why did we, and why might you need a router?

---

## One server in europe and one server in the USA.

---

![bg contain](images/1-1-dalle.png)

---

![bg contain](images/2-1-dalle.png)

---

![bg](images/1-before-router.png)

---

![bg](images/2-with-router.png)

---

![bg](images/template-001.jpeg)

## Requirements

- Can route a request to the correct region.

---

![bg](images/template-001.jpeg)

## Requirements

- Can route a request to the correct region.
- Source of truth for unique email and to which team that email belongs.

---

![bg](images/template-001.jpeg)

## Requirements

- Can route a request to the correct region.
- Source of truth for unique email and to which team that email belongs.
- Fast Lookups for routing.

---

![bg](images/template-001.jpeg)

## Approach

<!-- 8m -->

- Reverse Proxy.

---

![](https://cf-assets.www.cloudflare.com/slt3lc6tev37/3msJRtqxDysQslvrKvEf8x/f7f54c9a2cad3e4586f58e8e0e305389/reverse_proxy_flow.png)

---

![bg](images/template-001.jpeg)

## Approach

- Reverse Proxy.
- Single Postgres database in one region, this solves uniqueness.

---

![bg](images/template-001.jpeg)

## Approach

- Reverse Proxy.
- Single Postgres database in one region, this solves uniqueness.
- ETS cache in all regions, transported by Kafka, this solves fast lookups.

---

![bg](images/template-001.jpeg)

## Elixir Strengths

<!-- 14m -->

- Holding on to Connections

---

![bg](images/template-001.jpeg)

## Elixir Strengths

- Holding on to Connections
- Plug places the pit of success right in front of you.

---

![bg](images/template-001.jpeg)

## Falling in the pit of success, in our `router.ex` file.

```elixir
  pipeline :gandalf_proxy do
    plug(RegionDataAdder)
    plug(RegionAdder)
    plug(Parser)
    plug(Proxy)
    plug(SamlNameIdComparer)
    plug(Response)
  end
```

---

![bg](images/template-001.jpeg)

## Elixir Strengths

- Holding on to Connections.
- Plug places the pit of success right in front of you.
- Adds minimal latency.

---

![bg contain](images/Non-proxy-time-spent-in-Randalf.png)

---

![bg](images/template-001.jpeg)

## Pitfalls

- Hop-by-hop headers

---

![bg](images/template-001.jpeg)

## Pitfalls

- Hop-by-hop headers
- Flexing how much we can do with very little resources

---

![bg](images/template-001.jpeg)

## Pitfalls

- Hop-by-hop headers
- Flexing how much we can do with very little resources
- We could not cut any scope, and the project took longer than expected.

---

## Now What?

- Build a proxy, it will be easy.

---

## Now What?

- Build a proxy, it will be easy.
- If you need to build a router, consider how many different types of requests you need to route.
