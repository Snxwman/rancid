# Providers

# What are providers?

Providers are the underlying scripts, programs, and daemons that *provide* state information to eww.

Any particular widget has a single expected [state](state.md) from which it can pull data for use (defined as a `yuck` variable), 
but may have many providers for that state.

For example, a weather widget will expect to have a state variable named `weather` available, but the data in this variable may 
have been obtained through the [Tomorrow](https://tomorrow.io) API on one user's system, while another user may opt to use the 
[OpenWeatherMap](https://openweathermap.org) API for weather data.

In this example, `weather` is the [state](state.md#weather) while *tomorrow* or *openweathermap* are the providers.

This allows the same widget structure to be used by people using different backend services to provide the same or similar data.

# Adding a provider

Additional providers for already defined widgets **must** conform to the expected state.

