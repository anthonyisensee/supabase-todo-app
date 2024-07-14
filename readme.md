# Supabase Todo App

## Running Local Development (Windows & WSL)

First, complete the [Local Development Setup](#local-development-setup-windows--wsl) steps. Ensure Docker Desktop is running, and then run `supabase start` in the WSL2 shell. This will start the Docker container and display Supabase access information to the console.

## Local Development Setup (Windows & WSL)

### Installations

#### WSL2 & Ubuntu

Run `wsl --install` as an admin in a PowerShell shell. By default, installing WSL via this command installs WSL2 and an Ubuntu distribution that you can interact with via a WSL shell.

If additional information is needed, see [this guide](https://learn.microsoft.com/en-us/windows/wsl/install) for detailed steps to install WSL2.

WSL2 is required for Docker Desktop. If you have already installed WSL but are unsure of the version you can verify that you have WSL2 by running `wsl -l -v` in a PowerShell shell. If the value of the Ubuntu distribution in the "VERSION" column is listed as 2, you are good. If the command errors or a 2 is not shown, take the necessary steps to install WSL2 and/or upgrade from WSL1 to WSL2.

If you've already installed WSL2 but don't have an Ubuntu distribution, you can install Ubuntu with `wsl install -d ubuntu`. To see installed distributions, use `wsl -l`.

#### Homebrew

Homebrew does not come with Ubuntu and should be installed to enable easy installation of the Supabase CLI.

1. In a WSL shell, install homebrew via `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` (see https://brew.sh/).
2. Run the script produced by the above command to add homebrew to the path. It is recommended to copy from the console in case the script below has changed. This script is not included here so that the latest script is always run.

#### Docker Desktop

Download the Docker Desktop for Windows installer from https://www.docker.com/products/docker-desktop/. Run the installer and follow the steps to install.

By default, the "Use the WSL 2 based engine" setting is checked in the Docker Desktop settings if WSL2 is already installed. This will allow access of Docker via WSL shell. If Docker Desktop was installed prior to installing WSL2, ensure this setting is checked.

#### Supabase CLI

Install the Supabase CLI via `brew install supabase/tap/supabase`. (As a helpful note, you can update the CLI later by using `brew upgrade supabase`.)

(If you ever need to initialize a new Supabase project you can use the `supabase init` command in a WSL shell. However, once the `supabase` directory exists in a project, you only need to use `supabase start` to run the project. Note that the `supabase init` command will use the name of the containing directory as the name of the project.)

### Running the Application

Run `supabase start` in a WSL shell.

(If you run into the error "failed to start docker container: Error response from daemon: Ports are not available: exposing port TCP 0.0.0.0:54322 -> 0.0.0.0:0: listen tcp 0.0.0.0:54322: bind: An attempt was made to access a socket in a way forbidden by its access permissions." when running `supabase start` try running `net stop hns` and `net start hns` in Admin PowerShell. Then re-run `supabase start`.)
