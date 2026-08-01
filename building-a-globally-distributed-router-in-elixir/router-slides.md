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

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

# Building a Globally Distributed Router in Elixir

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Why did we, and why might you need a router?

---

## One server in europe and one server in the USA.

---

![bg contain](https://f000.backblazeb2.com/file/elixirconf-23/1-1-dalle.png)

---

![bg contain](https://f000.backblazeb2.com/file/elixirconf-23/2-1-dalle.png)

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/1-before-router.png)

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/2-with-router.png)

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Requirements

- Can route a request to the correct region.

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Requirements

- Can route a request to the correct region.
- Source of truth for unique email and to which team that email belongs.

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Requirements

- Can route a request to the correct region.
- Source of truth for unique email and to which team that email belongs.
- Fast Lookups for routing.

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Approach

<!-- 8m -->

- Reverse Proxy.

---

![](https://cf-assets.www.cloudflare.com/slt3lc6tev37/3msJRtqxDysQslvrKvEf8x/f7f54c9a2cad3e4586f58e8e0e305389/reverse_proxy_flow.png)

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Approach

- Reverse Proxy.
- Single Postgres database in one region, this solves uniqueness.

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Approach

- Reverse Proxy.
- Single Postgres database in one region, this solves uniqueness.
- ETS cache in all regions, transported by Kafka, this solves fast lookups.

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Elixir Strengths

<!-- 14m -->

- Holding on to Connections

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Elixir Strengths

- Holding on to Connections
- Plug places the pit of success right in front of you.

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

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

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Elixir Strengths

- Holding on to Connections.
- Plug places the pit of success right in front of you.
- Adds minimal latency.

---

![bg contain](https://f000.backblazeb2.com/file/elixirconf-23/Non-proxy-time-spent-in-Randalf.png)

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Pitfalls

- Hop-by-hop headers

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

## Pitfalls

- Hop-by-hop headers
- Flexing how much we can do with very little resources

---

![bg](https://f000.backblazeb2.com/file/elixirconf-23/template-%E2%80%8E001.jpeg)

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
