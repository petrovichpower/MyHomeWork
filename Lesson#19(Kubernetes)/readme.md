    1. Развернуть EKS кластер с помощью terraform, задеплоить mongodb используя подходящий тип поды.
C:\course devops>terraform plan
module.eks.data.aws_partition.current: Reading...
data.aws_availability_zones.available: Reading...
module.eks.module.kms.data.aws_caller_identity.current: Reading...
module.eks.module.kms.data.aws_partition.current: Reading...
module.eks.data.aws_caller_identity.current: Reading...
module.eks.module.eks_managed_node_group["one"].data.aws_caller_identity.current: Reading...
module.eks.module.eks_managed_node_group["one"].data.aws_partition.current: Reading...
module.eks.module.kms.data.aws_partition.current: Read complete after 0s [id=aws]
module.eks.data.aws_partition.current: Read complete after 0s [id=aws]
module.eks.module.eks_managed_node_group["one"].data.aws_partition.current: Read complete after 0s [id=aws]
module.vpc.aws_vpc.this[0]: Refreshing state... [id=vpc-0f12c5113fd3cf5d5]
module.eks.aws_cloudwatch_log_group.this[0]: Refreshing state... [id=/aws/eks/petrovich-tf-eks/cluster]
module.eks.data.aws_iam_policy_document.assume_role_policy[0]: Reading...
module.eks.module.eks_managed_node_group["one"].data.aws_iam_policy_document.assume_role_policy[0]: Reading...
module.eks.data.aws_iam_policy_document.assume_role_policy[0]: Read complete after 0s [id=2764486067]
module.eks.module.eks_managed_node_group["one"].data.aws_iam_policy_document.assume_role_policy[0]: Read complete after 0s [id=2560088296]
module.eks.aws_iam_role.this[0]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002]
module.eks.module.eks_managed_node_group["one"].aws_iam_role.this[0]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001]
data.aws_availability_zones.available: Read complete after 0s [id=us-east-1]
module.eks.module.kms.data.aws_caller_identity.current: Read complete after 0s [id=097084951758]
module.eks.module.eks_managed_node_group["one"].data.aws_caller_identity.current: Read complete after 1s [id=097084951758]
module.eks.data.aws_caller_identity.current: Read complete after 1s [id=097084951758]
module.eks.data.aws_iam_session_context.current: Reading...
module.eks.data.aws_iam_session_context.current: Read complete after 0s [id=arn:aws:iam::097084951758:user/petrovichpower]
module.eks.module.eks_managed_node_group["one"].aws_iam_role_policy_attachment.this["arn:aws:iam::aws:policy/AmazonEKS_CNI_Policy"]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001-20240423173931134700000005]
module.eks.module.eks_managed_node_group["one"].aws_iam_role_policy_attachment.this["arn:aws:iam::aws:policy/AmazonEKSWorkerNodePolicy"]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001-20240423173930945900000003]
module.eks.module.eks_managed_node_group["one"].aws_iam_role_policy_attachment.this["arn:aws:iam::aws:policy/AmazonEC2ContainerRegistryReadOnly"]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001-20240423173930958700000004]
module.eks.aws_iam_role_policy_attachment.this["AmazonEKSClusterPolicy"]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002-20240423173931558700000007]
module.eks.aws_iam_role_policy_attachment.this["AmazonEKSVPCResourceController"]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002-20240423173931506200000006]
module.eks.module.kms.data.aws_iam_policy_document.this[0]: Reading...
module.eks.module.kms.data.aws_iam_policy_document.this[0]: Read complete after 0s [id=3021190415]
module.eks.module.kms.aws_kms_key.this[0]: Refreshing state... [id=3665213b-e0e8-4159-80c3-37ed2b0d76f3]
module.vpc.aws_default_security_group.this[0]: Refreshing state... [id=sg-0d1c41472a1475504]
module.vpc.aws_default_route_table.default[0]: Refreshing state... [id=rtb-03573d50386d66559]
module.vpc.aws_subnet.public[0]: Refreshing state... [id=subnet-0ac334983788c6496]
module.vpc.aws_subnet.private[0]: Refreshing state... [id=subnet-0477aee4d341ab181]
module.vpc.aws_subnet.private[1]: Refreshing state... [id=subnet-098606ef567f87571]
module.vpc.aws_subnet.public[1]: Refreshing state... [id=subnet-0484226df909ddcd5]
module.vpc.aws_route_table.public[0]: Refreshing state... [id=rtb-05ae1c3a087a8e576]
module.vpc.aws_default_network_acl.this[0]: Refreshing state... [id=acl-0557dd16549adbfe2]
module.eks.aws_security_group.node[0]: Refreshing state... [id=sg-01bd7468561fd0eeb]
module.eks.aws_security_group.cluster[0]: Refreshing state... [id=sg-01ec68c1c4995df7c]
module.vpc.aws_internet_gateway.this[0]: Refreshing state... [id=igw-0829010a95b481231]
module.vpc.aws_route_table.private[0]: Refreshing state... [id=rtb-0802604ab17cff3aa]
module.eks.aws_security_group_rule.cluster["ingress_nodes_443"]: Refreshing state... [id=sgrule-748901595]
module.eks.aws_security_group_rule.node["ingress_cluster_9443_webhook"]: Refreshing state... [id=sgrule-2358084602]
module.eks.aws_security_group_rule.node["ingress_self_coredns_udp"]: Refreshing state... [id=sgrule-1021594806]
module.eks.aws_security_group_rule.node["ingress_nodes_ephemeral"]: Refreshing state... [id=sgrule-1427979656]
module.eks.aws_security_group_rule.node["egress_all"]: Refreshing state... [id=sgrule-3438531010]
module.eks.aws_security_group_rule.node["ingress_cluster_443"]: Refreshing state... [id=sgrule-3083089171]
module.eks.aws_security_group_rule.node["ingress_self_coredns_tcp"]: Refreshing state... [id=sgrule-2562453337]
module.eks.aws_security_group_rule.node["ingress_cluster_8443_webhook"]: Refreshing state... [id=sgrule-3895242801]
module.eks.aws_security_group_rule.node["ingress_cluster_kubelet"]: Refreshing state... [id=sgrule-3825809522]
module.eks.aws_security_group_rule.node["ingress_cluster_6443_webhook"]: Refreshing state... [id=sgrule-4218457104]
module.eks.aws_security_group_rule.node["ingress_cluster_4443_webhook"]: Refreshing state... [id=sgrule-842197894]
module.vpc.aws_route_table_association.public[1]: Refreshing state... [id=rtbassoc-0f844ea37fe24c03a]
module.vpc.aws_route_table_association.public[0]: Refreshing state... [id=rtbassoc-0b6e4e8f02e478166]
module.vpc.aws_route_table_association.private[0]: Refreshing state... [id=rtbassoc-001d97de4ca460b3d]
module.vpc.aws_route_table_association.private[1]: Refreshing state... [id=rtbassoc-0fb439e05d67324fc]
module.eks.module.kms.aws_kms_alias.this["cluster"]: Refreshing state... [id=alias/eks/petrovich-tf-eks]
module.vpc.aws_eip.nat[0]: Refreshing state... [id=eipalloc-0e1307e134cc969c0]
module.vpc.aws_route.public_internet_gateway[0]: Refreshing state... [id=r-rtb-05ae1c3a087a8e5761080289494]
module.eks.aws_iam_policy.cluster_encryption[0]: Refreshing state... [id=arn:aws:iam::097084951758:policy/petrovich-tf-eks-cluster-ClusterEncryption2024042317395131430000000b]
module.vpc.aws_nat_gateway.this[0]: Refreshing state... [id=nat-004db2e66a091b5f7]
module.eks.aws_eks_cluster.this[0]: Refreshing state... [id=petrovich-tf-eks]
module.eks.aws_iam_role_policy_attachment.cluster_encryption[0]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002-2024042317395224750000000c]
module.vpc.aws_route.private_nat_gateway[0]: Refreshing state... [id=r-rtb-0802604ab17cff3aa1080289494]
module.eks.time_sleep.this[0]: Refreshing state... [id=2024-04-23T18:20:01Z]
module.eks.aws_iam_openid_connect_provider.oidc_provider[0]: Refreshing state... [id=arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991]
module.eks.module.eks_managed_node_group["one"].aws_launch_template.this[0]: Refreshing state... [id=lt-09ccf490aebbf6ed2]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Refreshing state... [id=petrovich-tf-eks:petrovich-node-group-20240423182001942500000001]

Note: Objects have changed outside of Terraform

Terraform detected the following changes made outside of Terraform since the last "terraform apply" which may have
affected this plan:

  # module.eks.aws_eks_cluster.this[0] has been deleted
  - resource "aws_eks_cluster" "this" {
      - arn                       = "arn:aws:eks:us-east-1:097084951758:cluster/petrovich-tf-eks" -> null
      - certificate_authority     = [
          - {
              - data = "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURCVENDQWUyZ0F3SUJBZ0lJTnBYbVBab0pJQlF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TkRBME1qTXhPREV3TURSYUZ3MHpOREEwTWpFeE9ERTFNRFJhTUJVeApFekFSQmdOVkJBTVRDbXQxWW1WeWJtVjBaWE13Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBQTRJQkR3QXdnZ0VLCkFvSUJBUURJZ0N0bDIyOVhZMzZNNGF1MmNocEV3c1ZNMkluZUlTRHV0d3BaT1Q1VzVaYmNjTVdKeUFxaEVQZzQKVk1nWi82bEIwUUd2ZlVSeDdxeFJ3djNWRFVsOTJCbEFia3JUbnpNWHVXenN4aHY0TDE1VGJpSTBXMWlWa1hBbgo4eUFqSHcrU2RhNGxpUTdUbnNHMm5CQ0JQM2lFNVl5cjMwQWJWN0ErcXdqVzQ0RU9NSlhqSVBKbERMNVB3S3M0CnNwYnhMTForaU81UndBTi8zeXFURzBzS1RBYlptd3lQcE9SWlVscWFiUTVZVThTc01Mak5jcjExUXYxcHI5S2YKM3ZDOEsrU0RiNFVuNW5pRERWZTRTQWwyT0piTXJaNVN0YzhobWxQNis3VS9JZnRyK0RBNjFrVHB2dWFJcFNhagpPNjlsN3ZyRVlMTmZpV01sMGxDTFNHYUY5cWgxQWdNQkFBR2pXVEJYTUE0R0ExVWREd0VCL3dRRUF3SUNwREFQCkJnTlZIUk1CQWY4RUJUQURBUUgvTUIwR0ExVWREZ1FXQkJRQW5ZcDVrbVo0VzRlL0lWNFhRSHhBakxKQzJqQVYKQmdOVkhSRUVEakFNZ2dwcmRXSmxjbTVsZEdWek1BMEdDU3FHU0liM0RRRUJDd1VBQTRJQkFRQVZvMFJwMjFqaQpsREpsUVlKQVpaVUZmQ2oxVmtWUktjcG5TUWE0cFVRa1Z5MGdtK0g3Smc1K0VSR1pjeWdDNU53VjZib2p1R3EzCmlKY2dXVFVyS0NBMjNnbWorUjcxTEcvYXBDTy8za3BhRUdPQ01pNGp6c1lTdTBnZmhaRkd6YlEvUUg5ZVFwci8Kb0MxWmxRdURDUXpuWm9NaGZiWGtKRG55L254UnQ3ZllPQSttaFJGSndVTWNiTEdhZ05Uc2xqRUdvTEszR2NJQgptTnZ2T1doL3VEMGFJZUIyU2JzWkh0eFkyNDNHaVdJNVJ4ZklvaEpNK0lQL0FUWC91TllHUElja2Z0MGJGZnBDCjdiUEQ2ZVdPZTNmN01aYjN1RUJETFhFb2FYOGFxY3haVHNHdWV5V2dyRGREUkFOc3JERDJvNW5UN0ZCVzgxZTEKN0RhRm5hUjV4S0ZBCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K"
            },
        ] -> null
      - endpoint                  = "https://AB342C9D893B8D6814A6BF77C65C7991.gr7.us-east-1.eks.amazonaws.com" -> null
        id                        = "petrovich-tf-eks"
      - identity                  = [
          - {
              - oidc = [
                  - {
                      - issuer = "https://oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991"
                    },
                ]
            },
        ] -> null
      - name                      = "petrovich-tf-eks" -> null
      - platform_version          = "eks.6" -> null
      - status                    = "ACTIVE" -> null
      - version                   = "1.29" -> null
        # (4 unchanged attributes hidden)

      - vpc_config {
          - cluster_security_group_id = "sg-0acbeebc4ec72c74a" -> null
            # (6 unchanged attributes hidden)
        }

        # (3 unchanged blocks hidden)
    }

  # module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0] has been deleted
  - resource "aws_eks_node_group" "this" {
      - arn                    = "arn:aws:eks:us-east-1:097084951758:nodegroup/petrovich-tf-eks/petrovich-node-group-20240423182001942500000001/b0c78617-d84c-2bb1-041a-fb5b88cdd28b" -> null
      - id                     = "petrovich-tf-eks:petrovich-node-group-20240423182001942500000001" -> null
      - resources              = [
          - {
              - autoscaling_groups              = [
                  - {
                      - name = "eks-petrovich-node-group-20240423182001942500000001-b0c78617-d84c-2bb1-041a-fb5b88cdd28b"
                    },
                ]
                # (1 unchanged attribute hidden)
            },
        ] -> null
      - status                 = "ACTIVE" -> null
        tags                   = {
            "Name" = "petrovich-node-group"
        }
        # (12 unchanged attributes hidden)

        # (4 unchanged blocks hidden)
    }


Unless you have made equivalent changes to your configuration, or ignored the relevant attributes using ignore_changes,
the following plan may include actions to undo or respond to these changes.

───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the
following symbols:
  + create
-/+ destroy and then create replacement
+/- create replacement and then destroy
 <= read (data resources)

Terraform will perform the following actions:

  # module.eks.data.tls_certificate.this[0] will be read during apply
  # (config refers to values not yet known)
 <= data "tls_certificate" "this" {
      + certificates = (known after apply)
      + id           = (known after apply)
      + url          = (known after apply)
    }

  # module.eks.aws_eks_cluster.this[0] will be created
  + resource "aws_eks_cluster" "this" {
      + arn                       = (known after apply)
      + certificate_authority     = (known after apply)
      + cluster_id                = (known after apply)
      + created_at                = (known after apply)
      + enabled_cluster_log_types = [
          + "api",
          + "audit",
          + "authenticator",
        ]
      + endpoint                  = (known after apply)
      + id                        = (known after apply)
      + identity                  = (known after apply)
      + name                      = "petrovich-tf-eks"
      + platform_version          = (known after apply)
      + role_arn                  = "arn:aws:iam::097084951758:role/petrovich-tf-eks-cluster-20240423173929074500000002"      + status                    = (known after apply)
      + tags_all                  = (known after apply)
      + version                   = "1.29"

      + encryption_config {
          + resources = [
              + "secrets",
            ]

          + provider {
              + key_arn = "arn:aws:kms:us-east-1:097084951758:key/3665213b-e0e8-4159-80c3-37ed2b0d76f3"
            }
        }

      + kubernetes_network_config {
          + ip_family         = (known after apply)
          + service_ipv4_cidr = (known after apply)
          + service_ipv6_cidr = (known after apply)
        }

      + timeouts {}

      + vpc_config {
          + cluster_security_group_id = (known after apply)
          + endpoint_private_access   = true
          + endpoint_public_access    = true
          + public_access_cidrs       = [
              + "0.0.0.0/0",
            ]
          + security_group_ids        = [
              + "sg-01ec68c1c4995df7c",
            ]
          + subnet_ids                = [
              + "subnet-0477aee4d341ab181",
              + "subnet-098606ef567f87571",
            ]
          + vpc_id                    = (known after apply)
        }
    }

  # module.eks.aws_iam_openid_connect_provider.oidc_provider[0] must be replaced
-/+ resource "aws_iam_openid_connect_provider" "oidc_provider" {
      ~ arn             = "arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991" -> (known after apply)
      ~ id              = "arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991" -> (known after apply)
        tags            = {
            "Name" = "petrovich-tf-eks-eks-irsa"
        }
      ~ thumbprint_list = [
          - "9e99a48a9960b14926bb7f3b02e22da2b0ab7280",
          - "06b25927c42a721631c1efd9431e648fa62e1e39",
          - "414a2060b738c635cc7fc243e052615592830c53",
          - "aaa68bb211d468db8a8a19561ccba2e4043dcc80",
        ] -> (known after apply)
      ~ url             = "oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991" # forces replacement -> (known after apply) # forces replacement
        # (2 unchanged attributes hidden)
    }

  # module.eks.time_sleep.this[0] must be replaced
+/- resource "time_sleep" "this" {
      ~ id              = "2024-04-23T18:20:01Z" -> (known after apply)
      ~ triggers        = { # forces replacement
          ~ "cluster_certificate_authority_data" = "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURCVENDQWUyZ0F3SUJBZ0lJTnBYbVBab0pJQlF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TkRBME1qTXhPREV3TURSYUZ3MHpOREEwTWpFeE9ERTFNRFJhTUJVeApFekFSQmdOVkJBTVRDbXQxWW1WeWJtVjBaWE13Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBQTRJQkR3QXdnZ0VLCkFvSUJBUURJZ0N0bDIyOVhZMzZNNGF1MmNocEV3c1ZNMkluZUlTRHV0d3BaT1Q1VzVaYmNjTVdKeUFxaEVQZzQKVk1nWi82bEIwUUd2ZlVSeDdxeFJ3djNWRFVsOTJCbEFia3JUbnpNWHVXenN4aHY0TDE1VGJpSTBXMWlWa1hBbgo4eUFqSHcrU2RhNGxpUTdUbnNHMm5CQ0JQM2lFNVl5cjMwQWJWN0ErcXdqVzQ0RU9NSlhqSVBKbERMNVB3S3M0CnNwYnhMTForaU81UndBTi8zeXFURzBzS1RBYlptd3lQcE9SWlVscWFiUTVZVThTc01Mak5jcjExUXYxcHI5S2YKM3ZDOEsrU0RiNFVuNW5pRERWZTRTQWwyT0piTXJaNVN0YzhobWxQNis3VS9JZnRyK0RBNjFrVHB2dWFJcFNhagpPNjlsN3ZyRVlMTmZpV01sMGxDTFNHYUY5cWgxQWdNQkFBR2pXVEJYTUE0R0ExVWREd0VCL3dRRUF3SUNwREFQCkJnTlZIUk1CQWY4RUJUQURBUUgvTUIwR0ExVWREZ1FXQkJRQW5ZcDVrbVo0VzRlL0lWNFhRSHhBakxKQzJqQVYKQmdOVkhSRUVEakFNZ2dwcmRXSmxjbTVsZEdWek1BMEdDU3FHU0liM0RRRUJDd1VBQTRJQkFRQVZvMFJwMjFqaQpsREpsUVlKQVpaVUZmQ2oxVmtWUktjcG5TUWE0cFVRa1Z5MGdtK0g3Smc1K0VSR1pjeWdDNU53VjZib2p1R3EzCmlKY2dXVFVyS0NBMjNnbWorUjcxTEcvYXBDTy8za3BhRUdPQ01pNGp6c1lTdTBnZmhaRkd6YlEvUUg5ZVFwci8Kb0MxWmxRdURDUXpuWm9NaGZiWGtKRG55L254UnQ3ZllPQSttaFJGSndVTWNiTEdhZ05Uc2xqRUdvTEszR2NJQgptTnZ2T1doL3VEMGFJZUIyU2JzWkh0eFkyNDNHaVdJNVJ4ZklvaEpNK0lQL0FUWC91TllHUElja2Z0MGJGZnBDCjdiUEQ2ZVdPZTNmN01aYjN1RUJETFhFb2FYOGFxY3haVHNHdWV5V2dyRGREUkFOc3JERDJvNW5UN0ZCVzgxZTEKN0RhRm5hUjV4S0ZBCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K" -> (known after apply)
          ~ "cluster_endpoint"                   = "https://AB342C9D893B8D6814A6BF77C65C7991.gr7.us-east-1.eks.amazonaws.com" -> (known after apply)
            # (2 unchanged elements hidden)
        }
        # (1 unchanged attribute hidden)
    }

  # module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0] will be created
  + resource "aws_eks_node_group" "this" {
      + ami_type               = "AL2_x86_64"
      + arn                    = (known after apply)
      + capacity_type          = (known after apply)
      + cluster_name           = "petrovich-tf-eks"
      + disk_size              = (known after apply)
      + id                     = (known after apply)
      + instance_types         = [
          + "t3.small",
        ]
      + node_group_name        = (known after apply)
      + node_group_name_prefix = "petrovich-node-group-"
      + node_role_arn          = "arn:aws:iam::097084951758:role/petrovich-node-group-eks-node-group-20240423173929074000000001"
      + release_version        = (known after apply)
      + resources              = (known after apply)
      + status                 = (known after apply)
      + subnet_ids             = [
          + "subnet-0477aee4d341ab181",
          + "subnet-098606ef567f87571",
        ]
      + tags                   = {
          + "Name" = "petrovich-node-group"
        }
      + tags_all               = {
          + "Name" = "petrovich-node-group"
        }
      + version                = "1.29"

      + launch_template {
          + id      = "lt-09ccf490aebbf6ed2"
          + name    = (known after apply)
          + version = "1"
        }

      + scaling_config {
          + desired_size = 2
          + max_size     = 2
          + min_size     = 2
        }

      + timeouts {}

      + update_config {
          + max_unavailable_percentage = 33
        }
    }

Plan: 4 to add, 0 to change, 2 to destroy.

Changes to Outputs:
  ~ cluster_endpoint          = "https://AB342C9D893B8D6814A6BF77C65C7991.gr7.us-east-1.eks.amazonaws.com" -> (known after apply)

───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take exactly these actions if
you run "terraform apply" now.

C:\course devops>terraform apply
module.eks.module.kms.data.aws_caller_identity.current: Reading...
module.eks.module.eks_managed_node_group["one"].data.aws_caller_identity.current: Reading...
module.eks.data.aws_partition.current: Reading...
module.eks.module.kms.data.aws_partition.current: Reading...
module.eks.module.eks_managed_node_group["one"].data.aws_partition.current: Reading...
module.eks.data.aws_caller_identity.current: Reading...
data.aws_availability_zones.available: Reading...
module.vpc.aws_vpc.this[0]: Refreshing state... [id=vpc-0f12c5113fd3cf5d5]
module.eks.aws_cloudwatch_log_group.this[0]: Refreshing state... [id=/aws/eks/petrovich-tf-eks/cluster]
module.eks.data.aws_partition.current: Read complete after 0s [id=aws]
module.eks.module.kms.data.aws_partition.current: Read complete after 0s [id=aws]
module.eks.module.eks_managed_node_group["one"].data.aws_partition.current: Read complete after 0s [id=aws]
module.eks.data.aws_iam_policy_document.assume_role_policy[0]: Reading...
module.eks.module.eks_managed_node_group["one"].data.aws_iam_policy_document.assume_role_policy[0]: Reading...
module.eks.data.aws_iam_policy_document.assume_role_policy[0]: Read complete after 0s [id=2764486067]
module.eks.module.eks_managed_node_group["one"].data.aws_iam_policy_document.assume_role_policy[0]: Read complete after 0s [id=2560088296]
module.eks.aws_iam_role.this[0]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002]
module.eks.module.eks_managed_node_group["one"].aws_iam_role.this[0]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001]
module.eks.data.aws_caller_identity.current: Read complete after 1s [id=097084951758]
module.eks.data.aws_iam_session_context.current: Reading...
module.eks.data.aws_iam_session_context.current: Read complete after 0s [id=arn:aws:iam::097084951758:user/petrovichpower]
module.eks.module.eks_managed_node_group["one"].data.aws_caller_identity.current: Read complete after 1s [id=097084951758]
module.eks.module.kms.data.aws_caller_identity.current: Read complete after 1s [id=097084951758]
data.aws_availability_zones.available: Read complete after 1s [id=us-east-1]
module.eks.module.eks_managed_node_group["one"].aws_iam_role_policy_attachment.this["arn:aws:iam::aws:policy/AmazonEC2ContainerRegistryReadOnly"]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001-20240423173930958700000004]
module.eks.module.eks_managed_node_group["one"].aws_iam_role_policy_attachment.this["arn:aws:iam::aws:policy/AmazonEKS_CNI_Policy"]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001-20240423173931134700000005]
module.eks.module.eks_managed_node_group["one"].aws_iam_role_policy_attachment.this["arn:aws:iam::aws:policy/AmazonEKSWorkerNodePolicy"]: Refreshing state... [id=petrovich-node-group-eks-node-group-20240423173929074000000001-20240423173930945900000003]
module.eks.aws_iam_role_policy_attachment.this["AmazonEKSClusterPolicy"]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002-20240423173931558700000007]
module.eks.aws_iam_role_policy_attachment.this["AmazonEKSVPCResourceController"]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002-20240423173931506200000006]
module.eks.module.kms.data.aws_iam_policy_document.this[0]: Reading...
module.eks.module.kms.data.aws_iam_policy_document.this[0]: Read complete after 0s [id=3021190415]
module.eks.module.kms.aws_kms_key.this[0]: Refreshing state... [id=3665213b-e0e8-4159-80c3-37ed2b0d76f3]
module.vpc.aws_default_route_table.default[0]: Refreshing state... [id=rtb-03573d50386d66559]
module.vpc.aws_default_network_acl.this[0]: Refreshing state... [id=acl-0557dd16549adbfe2]
module.vpc.aws_default_security_group.this[0]: Refreshing state... [id=sg-0d1c41472a1475504]
module.vpc.aws_route_table.private[0]: Refreshing state... [id=rtb-0802604ab17cff3aa]
module.vpc.aws_subnet.private[1]: Refreshing state... [id=subnet-098606ef567f87571]
module.vpc.aws_internet_gateway.this[0]: Refreshing state... [id=igw-0829010a95b481231]
module.vpc.aws_subnet.public[1]: Refreshing state... [id=subnet-0484226df909ddcd5]
module.vpc.aws_subnet.public[0]: Refreshing state... [id=subnet-0ac334983788c6496]
module.eks.aws_security_group.node[0]: Refreshing state... [id=sg-01bd7468561fd0eeb]
module.vpc.aws_subnet.private[0]: Refreshing state... [id=subnet-0477aee4d341ab181]
module.eks.aws_security_group.cluster[0]: Refreshing state... [id=sg-01ec68c1c4995df7c]
module.vpc.aws_route_table.public[0]: Refreshing state... [id=rtb-05ae1c3a087a8e576]
module.vpc.aws_eip.nat[0]: Refreshing state... [id=eipalloc-0e1307e134cc969c0]
module.eks.module.kms.aws_kms_alias.this["cluster"]: Refreshing state... [id=alias/eks/petrovich-tf-eks]
module.eks.aws_iam_policy.cluster_encryption[0]: Refreshing state... [id=arn:aws:iam::097084951758:policy/petrovich-tf-eks-cluster-ClusterEncryption2024042317395131430000000b]
module.vpc.aws_route_table_association.private[0]: Refreshing state... [id=rtbassoc-001d97de4ca460b3d]
module.vpc.aws_route_table_association.private[1]: Refreshing state... [id=rtbassoc-0fb439e05d67324fc]
module.eks.aws_security_group_rule.node["ingress_self_coredns_udp"]: Refreshing state... [id=sgrule-1021594806]
module.eks.aws_security_group_rule.node["egress_all"]: Refreshing state... [id=sgrule-3438531010]
module.eks.aws_security_group_rule.node["ingress_cluster_kubelet"]: Refreshing state... [id=sgrule-3825809522]
module.eks.aws_security_group_rule.node["ingress_cluster_9443_webhook"]: Refreshing state... [id=sgrule-2358084602]
module.eks.aws_security_group_rule.node["ingress_nodes_ephemeral"]: Refreshing state... [id=sgrule-1427979656]
module.eks.aws_security_group_rule.node["ingress_cluster_6443_webhook"]: Refreshing state... [id=sgrule-4218457104]
module.eks.aws_security_group_rule.node["ingress_cluster_443"]: Refreshing state... [id=sgrule-3083089171]
module.eks.aws_security_group_rule.node["ingress_cluster_4443_webhook"]: Refreshing state... [id=sgrule-842197894]
module.eks.aws_security_group_rule.node["ingress_self_coredns_tcp"]: Refreshing state... [id=sgrule-2562453337]
module.eks.aws_security_group_rule.node["ingress_cluster_8443_webhook"]: Refreshing state... [id=sgrule-3895242801]
module.eks.aws_security_group_rule.cluster["ingress_nodes_443"]: Refreshing state... [id=sgrule-748901595]
module.vpc.aws_route_table_association.public[1]: Refreshing state... [id=rtbassoc-0f844ea37fe24c03a]
module.vpc.aws_route_table_association.public[0]: Refreshing state... [id=rtbassoc-0b6e4e8f02e478166]
module.vpc.aws_route.public_internet_gateway[0]: Refreshing state... [id=r-rtb-05ae1c3a087a8e5761080289494]
module.eks.aws_iam_role_policy_attachment.cluster_encryption[0]: Refreshing state... [id=petrovich-tf-eks-cluster-20240423173929074500000002-2024042317395224750000000c]
module.vpc.aws_nat_gateway.this[0]: Refreshing state... [id=nat-004db2e66a091b5f7]
module.vpc.aws_route.private_nat_gateway[0]: Refreshing state... [id=r-rtb-0802604ab17cff3aa1080289494]
module.eks.aws_eks_cluster.this[0]: Refreshing state... [id=petrovich-tf-eks]
module.eks.time_sleep.this[0]: Refreshing state... [id=2024-04-23T18:20:01Z]
module.eks.aws_iam_openid_connect_provider.oidc_provider[0]: Refreshing state... [id=arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991]
module.eks.module.eks_managed_node_group["one"].aws_launch_template.this[0]: Refreshing state... [id=lt-09ccf490aebbf6ed2]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Refreshing state... [id=petrovich-tf-eks:petrovich-node-group-20240423182001942500000001]

Note: Objects have changed outside of Terraform

Terraform detected the following changes made outside of Terraform since the last "terraform apply" which may have
affected this plan:

  # module.eks.aws_eks_cluster.this[0] has been deleted
  - resource "aws_eks_cluster" "this" {
      - arn                       = "arn:aws:eks:us-east-1:097084951758:cluster/petrovich-tf-eks" -> null
      - certificate_authority     = [
          - {
              - data = "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURCVENDQWUyZ0F3SUJBZ0lJTnBYbVBab0pJQlF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TkRBME1qTXhPREV3TURSYUZ3MHpOREEwTWpFeE9ERTFNRFJhTUJVeApFekFSQmdOVkJBTVRDbXQxWW1WeWJtVjBaWE13Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBQTRJQkR3QXdnZ0VLCkFvSUJBUURJZ0N0bDIyOVhZMzZNNGF1MmNocEV3c1ZNMkluZUlTRHV0d3BaT1Q1VzVaYmNjTVdKeUFxaEVQZzQKVk1nWi82bEIwUUd2ZlVSeDdxeFJ3djNWRFVsOTJCbEFia3JUbnpNWHVXenN4aHY0TDE1VGJpSTBXMWlWa1hBbgo4eUFqSHcrU2RhNGxpUTdUbnNHMm5CQ0JQM2lFNVl5cjMwQWJWN0ErcXdqVzQ0RU9NSlhqSVBKbERMNVB3S3M0CnNwYnhMTForaU81UndBTi8zeXFURzBzS1RBYlptd3lQcE9SWlVscWFiUTVZVThTc01Mak5jcjExUXYxcHI5S2YKM3ZDOEsrU0RiNFVuNW5pRERWZTRTQWwyT0piTXJaNVN0YzhobWxQNis3VS9JZnRyK0RBNjFrVHB2dWFJcFNhagpPNjlsN3ZyRVlMTmZpV01sMGxDTFNHYUY5cWgxQWdNQkFBR2pXVEJYTUE0R0ExVWREd0VCL3dRRUF3SUNwREFQCkJnTlZIUk1CQWY4RUJUQURBUUgvTUIwR0ExVWREZ1FXQkJRQW5ZcDVrbVo0VzRlL0lWNFhRSHhBakxKQzJqQVYKQmdOVkhSRUVEakFNZ2dwcmRXSmxjbTVsZEdWek1BMEdDU3FHU0liM0RRRUJDd1VBQTRJQkFRQVZvMFJwMjFqaQpsREpsUVlKQVpaVUZmQ2oxVmtWUktjcG5TUWE0cFVRa1Z5MGdtK0g3Smc1K0VSR1pjeWdDNU53VjZib2p1R3EzCmlKY2dXVFVyS0NBMjNnbWorUjcxTEcvYXBDTy8za3BhRUdPQ01pNGp6c1lTdTBnZmhaRkd6YlEvUUg5ZVFwci8Kb0MxWmxRdURDUXpuWm9NaGZiWGtKRG55L254UnQ3ZllPQSttaFJGSndVTWNiTEdhZ05Uc2xqRUdvTEszR2NJQgptTnZ2T1doL3VEMGFJZUIyU2JzWkh0eFkyNDNHaVdJNVJ4ZklvaEpNK0lQL0FUWC91TllHUElja2Z0MGJGZnBDCjdiUEQ2ZVdPZTNmN01aYjN1RUJETFhFb2FYOGFxY3haVHNHdWV5V2dyRGREUkFOc3JERDJvNW5UN0ZCVzgxZTEKN0RhRm5hUjV4S0ZBCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K"
            },
        ] -> null
      - endpoint                  = "https://AB342C9D893B8D6814A6BF77C65C7991.gr7.us-east-1.eks.amazonaws.com" -> null
        id                        = "petrovich-tf-eks"
      - identity                  = [
          - {
              - oidc = [
                  - {
                      - issuer = "https://oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991"
                    },
                ]
            },
        ] -> null
      - name                      = "petrovich-tf-eks" -> null
      - platform_version          = "eks.6" -> null
      - status                    = "ACTIVE" -> null
      - version                   = "1.29" -> null
        # (4 unchanged attributes hidden)

      - vpc_config {
          - cluster_security_group_id = "sg-0acbeebc4ec72c74a" -> null
            # (6 unchanged attributes hidden)
        }

        # (3 unchanged blocks hidden)
    }

  # module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0] has been deleted
  - resource "aws_eks_node_group" "this" {
      - arn                    = "arn:aws:eks:us-east-1:097084951758:nodegroup/petrovich-tf-eks/petrovich-node-group-20240423182001942500000001/b0c78617-d84c-2bb1-041a-fb5b88cdd28b" -> null
      - id                     = "petrovich-tf-eks:petrovich-node-group-20240423182001942500000001" -> null
      - resources              = [
          - {
              - autoscaling_groups              = [
                  - {
                      - name = "eks-petrovich-node-group-20240423182001942500000001-b0c78617-d84c-2bb1-041a-fb5b88cdd28b"
                    },
                ]
                # (1 unchanged attribute hidden)
            },
        ] -> null
      - status                 = "ACTIVE" -> null
        tags                   = {
            "Name" = "petrovich-node-group"
        }
        # (12 unchanged attributes hidden)

        # (4 unchanged blocks hidden)
    }


Unless you have made equivalent changes to your configuration, or ignored the relevant attributes using ignore_changes,
the following plan may include actions to undo or respond to these changes.

───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

Terraform used the selected providers to generate the following execution plan. Resource actions are indicated with the
following symbols:
  + create
-/+ destroy and then create replacement
+/- create replacement and then destroy
 <= read (data resources)

Terraform will perform the following actions:

  # module.eks.data.tls_certificate.this[0] will be read during apply
  # (config refers to values not yet known)
 <= data "tls_certificate" "this" {
      + certificates = (known after apply)
      + id           = (known after apply)
      + url          = (known after apply)
    }

  # module.eks.aws_eks_cluster.this[0] will be created
  + resource "aws_eks_cluster" "this" {
      + arn                       = (known after apply)
      + certificate_authority     = (known after apply)
      + cluster_id                = (known after apply)
      + created_at                = (known after apply)
      + enabled_cluster_log_types = [
          + "api",
          + "audit",
          + "authenticator",
        ]
      + endpoint                  = (known after apply)
      + id                        = (known after apply)
      + identity                  = (known after apply)
      + name                      = "petrovich-tf-eks"
      + platform_version          = (known after apply)
      + role_arn                  = "arn:aws:iam::097084951758:role/petrovich-tf-eks-cluster-20240423173929074500000002"      + status                    = (known after apply)
      + tags_all                  = (known after apply)
      + version                   = "1.29"

      + encryption_config {
          + resources = [
              + "secrets",
            ]

          + provider {
              + key_arn = "arn:aws:kms:us-east-1:097084951758:key/3665213b-e0e8-4159-80c3-37ed2b0d76f3"
            }
        }

      + kubernetes_network_config {
          + ip_family         = (known after apply)
          + service_ipv4_cidr = (known after apply)
          + service_ipv6_cidr = (known after apply)
        }

      + timeouts {}

      + vpc_config {
          + cluster_security_group_id = (known after apply)
          + endpoint_private_access   = true
          + endpoint_public_access    = true
          + public_access_cidrs       = [
              + "0.0.0.0/0",
            ]
          + security_group_ids        = [
              + "sg-01ec68c1c4995df7c",
            ]
          + subnet_ids                = [
              + "subnet-0477aee4d341ab181",
              + "subnet-098606ef567f87571",
            ]
          + vpc_id                    = (known after apply)
        }
    }

  # module.eks.aws_iam_openid_connect_provider.oidc_provider[0] must be replaced
-/+ resource "aws_iam_openid_connect_provider" "oidc_provider" {
      ~ arn             = "arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991" -> (known after apply)
      ~ id              = "arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991" -> (known after apply)
        tags            = {
            "Name" = "petrovich-tf-eks-eks-irsa"
        }
      ~ thumbprint_list = [
          - "9e99a48a9960b14926bb7f3b02e22da2b0ab7280",
          - "06b25927c42a721631c1efd9431e648fa62e1e39",
          - "414a2060b738c635cc7fc243e052615592830c53",
          - "aaa68bb211d468db8a8a19561ccba2e4043dcc80",
        ] -> (known after apply)
      ~ url             = "oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991" # forces replacement -> (known after apply) # forces replacement
        # (2 unchanged attributes hidden)
    }

  # module.eks.time_sleep.this[0] must be replaced
+/- resource "time_sleep" "this" {
      ~ id              = "2024-04-23T18:20:01Z" -> (known after apply)
      ~ triggers        = { # forces replacement
          ~ "cluster_certificate_authority_data" = "LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSURCVENDQWUyZ0F3SUJBZ0lJTnBYbVBab0pJQlF3RFFZSktvWklodmNOQVFFTEJRQXdGVEVUTUJFR0ExVUUKQXhNS2EzVmlaWEp1WlhSbGN6QWVGdzB5TkRBME1qTXhPREV3TURSYUZ3MHpOREEwTWpFeE9ERTFNRFJhTUJVeApFekFSQmdOVkJBTVRDbXQxWW1WeWJtVjBaWE13Z2dFaU1BMEdDU3FHU0liM0RRRUJBUVVBQTRJQkR3QXdnZ0VLCkFvSUJBUURJZ0N0bDIyOVhZMzZNNGF1MmNocEV3c1ZNMkluZUlTRHV0d3BaT1Q1VzVaYmNjTVdKeUFxaEVQZzQKVk1nWi82bEIwUUd2ZlVSeDdxeFJ3djNWRFVsOTJCbEFia3JUbnpNWHVXenN4aHY0TDE1VGJpSTBXMWlWa1hBbgo4eUFqSHcrU2RhNGxpUTdUbnNHMm5CQ0JQM2lFNVl5cjMwQWJWN0ErcXdqVzQ0RU9NSlhqSVBKbERMNVB3S3M0CnNwYnhMTForaU81UndBTi8zeXFURzBzS1RBYlptd3lQcE9SWlVscWFiUTVZVThTc01Mak5jcjExUXYxcHI5S2YKM3ZDOEsrU0RiNFVuNW5pRERWZTRTQWwyT0piTXJaNVN0YzhobWxQNis3VS9JZnRyK0RBNjFrVHB2dWFJcFNhagpPNjlsN3ZyRVlMTmZpV01sMGxDTFNHYUY5cWgxQWdNQkFBR2pXVEJYTUE0R0ExVWREd0VCL3dRRUF3SUNwREFQCkJnTlZIUk1CQWY4RUJUQURBUUgvTUIwR0ExVWREZ1FXQkJRQW5ZcDVrbVo0VzRlL0lWNFhRSHhBakxKQzJqQVYKQmdOVkhSRUVEakFNZ2dwcmRXSmxjbTVsZEdWek1BMEdDU3FHU0liM0RRRUJDd1VBQTRJQkFRQVZvMFJwMjFqaQpsREpsUVlKQVpaVUZmQ2oxVmtWUktjcG5TUWE0cFVRa1Z5MGdtK0g3Smc1K0VSR1pjeWdDNU53VjZib2p1R3EzCmlKY2dXVFVyS0NBMjNnbWorUjcxTEcvYXBDTy8za3BhRUdPQ01pNGp6c1lTdTBnZmhaRkd6YlEvUUg5ZVFwci8Kb0MxWmxRdURDUXpuWm9NaGZiWGtKRG55L254UnQ3ZllPQSttaFJGSndVTWNiTEdhZ05Uc2xqRUdvTEszR2NJQgptTnZ2T1doL3VEMGFJZUIyU2JzWkh0eFkyNDNHaVdJNVJ4ZklvaEpNK0lQL0FUWC91TllHUElja2Z0MGJGZnBDCjdiUEQ2ZVdPZTNmN01aYjN1RUJETFhFb2FYOGFxY3haVHNHdWV5V2dyRGREUkFOc3JERDJvNW5UN0ZCVzgxZTEKN0RhRm5hUjV4S0ZBCi0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0K" -> (known after apply)
          ~ "cluster_endpoint"                   = "https://AB342C9D893B8D6814A6BF77C65C7991.gr7.us-east-1.eks.amazonaws.com" -> (known after apply)
            # (2 unchanged elements hidden)
        }
        # (1 unchanged attribute hidden)
    }

  # module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0] will be created
  + resource "aws_eks_node_group" "this" {
      + ami_type               = "AL2_x86_64"
      + arn                    = (known after apply)
      + capacity_type          = (known after apply)
      + cluster_name           = "petrovich-tf-eks"
      + disk_size              = (known after apply)
      + id                     = (known after apply)
      + instance_types         = [
          + "t3.small",
        ]
      + node_group_name        = (known after apply)
      + node_group_name_prefix = "petrovich-node-group-"
      + node_role_arn          = "arn:aws:iam::097084951758:role/petrovich-node-group-eks-node-group-20240423173929074000000001"
      + release_version        = (known after apply)
      + resources              = (known after apply)
      + status                 = (known after apply)
      + subnet_ids             = [
          + "subnet-0477aee4d341ab181",
          + "subnet-098606ef567f87571",
        ]
      + tags                   = {
          + "Name" = "petrovich-node-group"
        }
      + tags_all               = {
          + "Name" = "petrovich-node-group"
        }
      + version                = "1.29"

      + launch_template {
          + id      = "lt-09ccf490aebbf6ed2"
          + name    = (known after apply)
          + version = "1"
        }

      + scaling_config {
          + desired_size = 2
          + max_size     = 2
          + min_size     = 2
        }

      + timeouts {}

      + update_config {
          + max_unavailable_percentage = 33
        }
    }

Plan: 4 to add, 0 to change, 2 to destroy.

Changes to Outputs:
  ~ cluster_endpoint          = "https://AB342C9D893B8D6814A6BF77C65C7991.gr7.us-east-1.eks.amazonaws.com" -> (known after apply)

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

module.eks.aws_iam_openid_connect_provider.oidc_provider[0]: Destroying... [id=arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AB342C9D893B8D6814A6BF77C65C7991]
module.eks.aws_iam_openid_connect_provider.oidc_provider[0]: Destruction complete after 1s
module.eks.aws_eks_cluster.this[0]: Creating...
module.eks.aws_eks_cluster.this[0]: Still creating... [10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [1m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [1m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [1m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [1m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [1m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [1m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [2m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [2m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [2m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [2m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [2m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [2m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [3m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [3m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [3m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [3m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [3m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [3m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [4m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [4m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [4m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [4m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [4m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [4m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [5m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [5m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [5m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [5m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [5m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [5m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [6m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [6m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [6m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [6m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [6m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [6m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [7m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [7m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [7m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [7m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [7m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [7m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [8m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [8m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [8m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [8m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [8m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [8m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [9m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [9m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [9m20s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [9m30s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [9m40s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [9m50s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [10m0s elapsed]
module.eks.aws_eks_cluster.this[0]: Still creating... [10m10s elapsed]
module.eks.aws_eks_cluster.this[0]: Creation complete after 10m17s [id=petrovich-tf-eks]
module.eks.data.tls_certificate.this[0]: Reading...
module.eks.time_sleep.this[0]: Creating...
module.eks.data.tls_certificate.this[0]: Read complete after 0s [id=5933588ce34e24e9fb40c3565fb0b5993639df67]
module.eks.aws_iam_openid_connect_provider.oidc_provider[0]: Creating...
module.eks.aws_iam_openid_connect_provider.oidc_provider[0]: Creation complete after 2s [id=arn:aws:iam::097084951758:oidc-provider/oidc.eks.us-east-1.amazonaws.com/id/AF5695043AE20F18301C48926D57CA87]
module.eks.time_sleep.this[0]: Still creating... [10s elapsed]
module.eks.time_sleep.this[0]: Still creating... [20s elapsed]
module.eks.time_sleep.this[0]: Creation complete after 30s [id=2024-04-24T11:03:12Z]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Creating...
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [10s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [20s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [30s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [40s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [50s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [1m0s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [1m10s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [1m20s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [1m30s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Still creating... [1m40s elapsed]
module.eks.module.eks_managed_node_group["one"].aws_eks_node_group.this[0]: Creation complete after 1m50s [id=petrovich-tf-eks:petrovich-node-group-20240424110312701100000001]
module.eks.time_sleep.this[0] (deposed object b3e59dac): Destroying... [id=2024-04-23T18:20:01Z]
module.eks.time_sleep.this[0]: Destruction complete after 0s

Apply complete! Resources: 4 added, 0 changed, 2 destroyed.

Outputs:

cluster_endpoint = "https://AF5695043AE20F18301C48926D57CA87.gr7.us-east-1.eks.amazonaws.com"
cluster_security_group_id = "sg-01ec68c1c4995df7c"
petrovich-tf-eks = "petrovich-tf-eks"
region = "us-east-1"


aws eks update-kubeconfig --name petrovich-tf-eks
Updated context arn:aws:eks:us-east-1:097084951758:cluster/petrovich-tf-eks in C:\Users\perfe\.kube\config

C:\mongo>kubectl apply -f mongodb-pv.yaml
persistentvolume/mongo-pv-volume created

C:\mongo>kubectl apply -f mongodb-secrets.yaml
secret/mongo-secret created

C:\mongo>kubectl apply -f mongodb-pvc.yaml
persistentvolumeclaim/mongo-pv-claim created

C:\mongo>kubectl apply -f mongodb-deployment.yaml
statefulset.apps/mongo created

C:\mongo>kubectl get pods
NAME      READY   STATUS    RESTARTS   AGE
mongo-0   1/1     Running   0          15s

    2. Подключить кластер к Lens.

![scr](https://github.com/petrovichpower/MyHomeWork/blob/main/Lesson%2319(Kubernetes)/Снимок%20экрана%202024-04-24%20142112.png)
