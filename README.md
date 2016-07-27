# Wechat

Wechat API wrapper in Elixir.

## Installation

If [available in Hex](https://hex.pm/docs/publish), the package can be installed as:

  1. Add `wechat` to your list of dependencies in `mix.exs`:

    ```elixir
    def deps do
      [{:wechat, "~> 0.1.0"}]
    end
    ```

  2. Ensure `wechat` is started before your application:

    ```elixir
    def application do
      [applications: [:wechat]]
    end
    ```

## Config

Add config in `config.exs`:

  ```
  config :wechat, Wechat,
    appid: "wechat app id",
    secret: "wechat app secret"
  ```

## Usage

```
> iex -S mix

iex> Wechat.access_token
"Bgw6_cMvFrE3hY3J8U6oglhvlzHhMpAQma0Wjam4XsLx8F6XP4pfZzsezBdpfth2BNAdUK6wA23S7D3fSePt7meG9a1gf9LhEmXjxGelnTjJLaIQMYumrCHE_9gcFVXaHIHcAGACDC"

iex> Wechat.User.list
%{count: 4,
  data: %{openid: ["oi00OuFrmNEC-QMa0Kikycq6A7ys",
     "oi00OuKAhA8bm5okpaIDs7WmUZr4", "oi00OuOdjK0TicVUmovudbSP5Zq4",
     "oi00OuBgG2mko_pOukCy00EYCwo4"]},
  next_openid: "oi00OuBgG2mko_pOukCy00EYCwo4", total: 4}

iex> Wechat.User.info("oi00OuKAhA8bm5okpaIDs7WmUZr4")
%{city: "宝山", country: "中国", groupid: 0,
  headimgurl: "http://wx.qlogo.cn/mmopen/7raJSSs9gLVJibia6sAXRvr8jajXfQFWiagrLwrRIZjMHCEXOxYf6nflxcpl4WkT7gz8Sa4tO32avnI0dlNLn24yA/0",
  language: "zh_CN", nickname: "小爆炸的爸爸",
  openid: "oi00OuKAhA8bm5okpaIDs7WmUZr4", province: "上海", remark: "",
  sex: 1, subscribe: 1, subscribe_time: 1449812483, tagid_list: [],
  unionid: "o2oUsuOUzgNL-JSLtIp8b3FzkI-M"}

iex> Wechat.Media.download("GuSq91L0FXQFOIFtKwX2i5UPXH9QKnnu63_z4JHZwIw3TMIn1C-xm8hX3nPWCA")
%{errcode: 40007, errmsg: "invalid media_id hint: [uJTJra0597e297]"}
```
