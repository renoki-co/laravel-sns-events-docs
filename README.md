---
description: >-
  Laravel SNS Events eases the processing of incoming SNS webhooks using Laravel
  Events.
---

# ⚡ Introduction

![](.gitbook/assets/Laravel\_SNS\_1\_25.png)

[![CI](https://github.com/renoki-co/laravel-sns-events/workflows/CI/badge.svg?branch=master)](https://github.com/renoki-co/laravel-sns-events/workflows/CI/badge.svg?branch=master) [![codecov](https://camo.githubusercontent.com/7e1f5403788f33a197bdb0efcddef2f8587aa510e72b08b5a65a03aa74823c12/68747470733a2f2f636f6465636f762e696f2f67682f72656e6f6b692d636f2f6c61726176656c2d736e732d6576656e74732f6272616e63682f6d61737465722f67726170682f62616467652e737667)](https://codecov.io/gh/renoki-co/laravel-sns-events/branch/master) [![StyleCI](https://camo.githubusercontent.com/eca224ed58aab402cc2dc124a62c6d47c4cc2ae43a546914f2959b33bbd080ab/68747470733a2f2f6769746875622e7374796c6563692e696f2f7265706f732f3138393235343937372f736869656c643f6272616e63683d6d6173746572)](https://github.styleci.io/repos/189254977) [![Latest Stable Version](https://camo.githubusercontent.com/ae2510cd6e9fcb114a8c5e8c0aa5361b42da54523b5f8d01c8a0eea52e184a11/68747470733a2f2f706f7365722e707567782e6f72672f72656e6e6f6b6b692f6c61726176656c2d736e732d6576656e74732f762f737461626c65)](https://packagist.org/packages/rennokki/laravel-sns-events) [![Total Downloads](https://camo.githubusercontent.com/370cd274d1c7f279fa56c3bf3ebcb49d3083df65b8f05ffebfbeeb1f53443706/68747470733a2f2f706f7365722e707567782e6f72672f72656e6e6f6b6b692f6c61726176656c2d736e732d6576656e74732f646f776e6c6f616473)](https://packagist.org/packages/rennokki/laravel-sns-events) [![Monthly Downloads](https://camo.githubusercontent.com/ecc8d9b65dc110c5f77e37659563796f23e91b34c304529b4faa2da2e4c2adc3/68747470733a2f2f706f7365722e707567782e6f72672f72656e6e6f6b6b692f6c61726176656c2d736e732d6576656e74732f642f6d6f6e74686c79)](https://packagist.org/packages/rennokki/laravel-sns-events) [![License](https://camo.githubusercontent.com/08c8c65db6b473bc63604467fcd1bbcc5dbb5ada05d337bd8494d39a8070fad6/68747470733a2f2f706f7365722e707567782e6f72672f72656e6e6f6b6b692f6c61726176656c2d736e732d6576656e74732f6c6963656e7365)](https://packagist.org/packages/rennokki/laravel-sns-events)

Laravel SNS Events eases the processing of incoming SNS webhooks using Laravel Events. It leverages a controller that is made to properly listen to SNS HTTP(s) webhooks and trigger events on which you can handle in Laravel, so you just have to focus on writing your logic to handle the events.
