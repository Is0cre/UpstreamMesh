# UpstreamMesh

Self-funded flood sensing on a LoRa mesh. The first build is five nodes, paid for by one person, left outside until they die. The result is the log.

The public site is the HTML in this repository: [upstreammesh.org](https://upstreammesh.org/).

## What this is

A plan for river corridors where the mast, the mains, and the cloud fail first. Two upstream nodes have to agree that the water is rising. A ridge relay carries the frame. A gateway keeps a copy. The end of the valley gets a buzzer if a person is there. A siren or a household watch only if someone who lives there asks.

The radio layer we are building on is [MeshCore](https://github.com/meshcore-dev/MeshCore), the open LoRa mesh from [meshcore-dev](https://github.com/meshcore-dev). UpstreamMesh is the flood sensing and the household warning on top of that. This repository does not maintain MeshCore, and it is not a MeshCore product.

- Library and firmware: [github.com/meshcore-dev/MeshCore](https://github.com/meshcore-dev/MeshCore) (MIT)
- Project site: [meshcore.io](https://meshcore.io)
- Flasher: [meshcore.io/flasher](https://meshcore.io/flasher)
- Docs: [docs.meshcore.io](https://docs.meshcore.io)

MeshCore already has companion, repeater, room, and sensor roles. Which of those match the five nodes below is still open.

## What this is not

- Not a deployment. No boards have been bought. No sites have been chosen. Nothing in this repository is a measured radio link.
- Not a live feed, a packet capture, or a municipal warning system.
- Not MeshCore's packet format. The 12-byte layout in [docs/frame.md](docs/frame.md) is a draft of what a flood frame would carry *inside* that mesh. It is not implemented.
- Not licensed yet. There is no `LICENSE` file. Firmware is not in this repository. Do not treat the text or the study images as reusable under an open-source license until one is added.
- The flood photographs are historical pictures from the Philippines. They are not pictures of this project.

## The first five

| Node | Job |
| --- | --- |
| N01 | Reads the river. Does not raise an alert alone. |
| N02 | Reads it again. Both have to agree. |
| N03 | Radio on a ridge. No sensor. |
| N04 | Keeps the log. A laptop while someone is there. Flash after that. |
| N05 | End of the valley. A buzzer for the test. Not a siren left alone. |

Before they are left: a bucket at N01 has to reach N05 with no phone in the path, and pulling the battery on N02 still has to deliver the frame the long way. Each box gets a note in the language spoken there. That language is not chosen yet.

Power is LiFePO4 and a small panel, mounted above the flood, closed with a gasket and screws so a dead node can be opened. The diary in flash is voltage, time awake, and the last restart. Detail is in [docs/first-five.md](docs/first-five.md) and on [build.html](build.html).

## The site

Plain HTML, one stylesheet, no build step. GitHub Pages serves the repository root.

| Page | File |
| --- | --- |
| Home | [index.html](index.html) |
| Why | [why.html](why.html) |
| The five | [build.html](build.html) |
| Protocol | [protocol.html](protocol.html) |
| Hardware | [hardware.html](hardware.html) |
| Contact | [contact.html](contact.html) |

The wordmark is the word `upstreammesh`: `upstream` in river blue, `mesh` in clay. [style.css](style.css) is the light paper theme. [favicon.svg](favicon.svg) is the small mark.

## Photographs

Stored in the repo so the site does not depend on a hotlink. Captions on [why.html](why.html) repeat this.

| File | What it shows | Credit |
| --- | --- | --- |
| [images/flood-vamco.jpg](images/flood-vamco.jpg) | Floodwater in Gatbuca and Frances, Calumpit, Bulacan, Typhoon Vamco (Ulysses), 13 November 2020 | Judgefloro, [CC0](https://creativecommons.org/publicdomain/zero/1.0/), [Commons](https://commons.wikimedia.org/wiki/File:273Effects_(floods)_of_Typhoon_Vamco_Calumpit,_Bulacan_21.jpg) |
| [images/flood-ondoy.jpg](images/flood-ondoy.jpg) | Flooding from Typhoon Ondoy (Ketsana), Philippines, 6 October 2009 | AusAID / Australian Department of Foreign Affairs and Trade, [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/), [Commons](https://commons.wikimedia.org/wiki/File:Flooding_from_Typhoon_Ondoy_(Ketsana),_Philippines_2009._Photo-_AusAID_(10695673035).jpg) |
| [images/flood-bopha.jpg](images/flood-bopha.jpg) | Homes destroyed by Typhoon Bopha (Pablo), Cateel, Davao Oriental, 6 December 2012 | Sonny Day, [CC BY 2.0](https://creativecommons.org/licenses/by/2.0/), [Commons](https://commons.wikimedia.org/wiki/File:Homes_destroyed_by_Typhoon_Bopha_in_Cateel,_Davao_Oriental.jpg) |

Bopha is typhoon rubble in Mindanao, not a river flood in Cagayan. None of the three is a picture of the pilot.

[images/node.jpg](images/node.jpg), [images/basin.jpg](images/basin.jpg), and [images/watch.jpg](images/watch.jpg) are study illustrations made for the page: a field box, a river gorge used as the model backdrop, and a screenless wrist device. They are not photographs of hardware.

## Publish

The site is already deployed from `main`, folder `/ (root)`, custom domain `upstreammesh.org`. [CNAME](CNAME) pins that name. `.nojekyll` is here so Pages does not run Jekyll.

DNS at the registrar:

| Host | Type | Value |
| --- | --- | --- |
| `@` | A | `185.199.108.153` |
| `@` | A | `185.199.109.153` |
| `@` | A | `185.199.110.153` |
| `@` | A | `185.199.111.153` |
| `www` | CNAME | `Is0cre.github.io` |

Do not put a CNAME record on `@`. AAAA records for the apex are optional:

`2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`.

## Contact

The form on [contact.html](contact.html) posts to the maintainer. Opening an [issue](https://github.com/Is0cre/UpstreamMesh/issues/new) does not depend on that form. The form provider sends an activation message before the first real letter is delivered.
