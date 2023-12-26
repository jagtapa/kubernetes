KUBECTL COMMANDS

# To detect api which are depricated or using specific old beta versions /beta2, beta3


kubectl get --raw /metrics | grep beta2 | grep HorizontalPodAutoscaler


apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="1024"} 19412
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="2048"} 19412
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="4096"} 291683
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="8192"} 291683
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="16384"} 291683
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="32768"} 291683
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="65536"} 291683
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="131072"} 291683
apiserver_watch_events_sizes_bucket{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2",le="+Inf"} 291683
apiserver_watch_events_sizes_sum{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2"} 8.74216083e+08
apiserver_watch_events_sizes_count{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2"} 291683
apiserver_watch_events_total{group="autoscaling",kind="HorizontalPodAutoscaler",version="v2beta2"} 291683
