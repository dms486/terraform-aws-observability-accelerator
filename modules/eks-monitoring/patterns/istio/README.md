# Istio patterns module

Provides monitoring for Istio based workloads with the following resources:

- AWS Managed Grafana Dashboard and data source
- Alerts and recording rules with AWS Managed Service for Prometheus

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.1.0 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 4.0.0 |
| <a name="requirement_helm"></a> [helm](#requirement\_helm) | >= 2.4.1 |
| <a name="requirement_kubectl"></a> [kubectl](#requirement\_kubectl) | >= 2.0.3 |
| <a name="requirement_kubernetes"></a> [kubernetes](#requirement\_kubernetes) | >= 2.10 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 4.0.0 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_prometheus_rule_group_namespace.alerting_rules](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/prometheus_rule_group_namespace) | resource |
| [aws_prometheus_rule_group_namespace.recording_rules](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/prometheus_rule_group_namespace) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_pattern_config"></a> [pattern\_config](#input\_pattern\_config) | Configuration object for ISTIO monitoring | <pre>object({<br>    enable_alerting_rules  = bool<br>    enable_recording_rules = bool<br>    enable_dashboards      = bool<br>    scrape_sample_limit    = number<br><br>    flux_gitrepository_name   = string<br>    flux_gitrepository_url    = string<br>    flux_gitrepository_branch = string<br>    flux_kustomization_name   = string<br>    flux_kustomization_path   = string<br><br>    managed_prometheus_workspace_id = string<br>    prometheus_metrics_endpoint     = string<br><br>    dashboards = object({<br>      cp          = string<br>      mesh        = string<br>      performance = string<br>      service     = string<br>    })<br>  })</pre> | n/a | yes |

## Outputs

No outputs.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
