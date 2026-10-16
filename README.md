# surface_reconstruction_msgs

ROS 2 interfaces used by the `surface_reconstruction` package (separate repository).

## Services

### `SaveMesh.srv`

Saves the mesh reconstructed by `cloud_merger_node` to a file (service `/cloud_merger_node/save`).

| Field | Type | Description |
|---|---|---|
| `filename` (request) | `string` | file path; the extension selects the format: `.ply` (binary), `.vtk`, `.obj`. If empty, the node parameter `default_mesh_file` is used |
| `success` (response) | `bool` | outcome of the save |
| `message` (response) | `string` | description of the outcome or of the error |

Example:

```bash
ros2 service call /cloud_merger_node/save surface_reconstruction_msgs/srv/SaveMesh "{filename: '/tmp/surface.ply'}"
```

The services without arguments (`acquire`, `remove_last`, `compute_surface`, `reset`) use `std_srvs/srv/Trigger`
and need no definition in this package.

## Authors

Developed by **CARI-JRL**.

Developer and maintainer: Manuel Beschi (<manuel.beschi@unibs.it>)

## License

Apache License 2.0, see [LICENSE](LICENSE).

Copyright 2026 CARI-JRL
