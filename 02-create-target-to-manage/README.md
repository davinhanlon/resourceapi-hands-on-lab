# Create Target to Manage

Need to have something that can be managed via an API. The first iteration of this is to use a Nest thermostat and get and set data on it. For the final public version it will make more sense to have something else that is easily accessible. Must be easy for people to use in a lab environment and give real-time feedback so people can see the results instantly.

Goals: get and set some data via an API to a remote target.

TODO

Create an application that has a Rest API - get some data and set some data.

Needs to be easy to set up, create an account, because all steps must be in the tutorial.

Must be real, in that there should be a simulator or emulator that allows the results to be easily displayed for instant feedback.

Alternative would be to have a docker container that’s running a web app with a REST api that participants can communicate with. Creates a dependency on Docker, but that could be overcome by providing the web application in a repo of its own, if people objected to Docker.

[03. Install the PDK](../03-install-pdk)
