<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-6">
        <!-- AREA CHART -->
        <div class="card card-primary">
          <div class="card-header">
            <h3 class="card-title">Area Chart</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div class="card-body">
            <div class="chart">
              <div class="chartjs-size-monitor">
                <div class="chartjs-size-monitor-expand">
                  <div class></div>
                </div>
                <div class="chartjs-size-monitor-shrink">
                  <div class></div>
                </div>
              </div>
              <canvas
                id="areaChart"
                style="height: 250px; min-height: 250px; display: block; width: 571px;"
                width="571"
                height="250"
                class="chartjs-render-monitor"
              ></canvas>
            </div>
          </div>
          <!-- /.card-body -->
        </div>
        <!-- /.card -->

        <!-- DONUT CHART -->
        <div class="card card-danger">
          <div class="card-header">
            <h3 class="card-title">Donut Chart</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div class="card-body">
            <div class="chartjs-size-monitor">
              <div class="chartjs-size-monitor-expand">
                <div class></div>
              </div>
              <div class="chartjs-size-monitor-shrink">
                <div class></div>
              </div>
            </div>
            <canvas
              id="donutChart"
              style="height: 230px; min-height: 230px; display: block; width: 571px;"
              width="571"
              height="230"
              class="chartjs-render-monitor"
            ></canvas>
          </div>
          <!-- /.card-body -->
        </div>
        <!-- /.card -->

        <!-- PIE CHART -->
        <div class="card card-danger">
          <div class="card-header">
            <h3 class="card-title">Pie Chart</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div class="card-body">
            <div class="chartjs-size-monitor">
              <div class="chartjs-size-monitor-expand">
                <div class></div>
              </div>
              <div class="chartjs-size-monitor-shrink">
                <div class></div>
              </div>
            </div>
            <canvas
              id="pieChart"
              style="height: 230px; min-height: 230px; display: block; width: 571px;"
              width="571"
              height="230"
              class="chartjs-render-monitor"
            ></canvas>
          </div>
          <!-- /.card-body -->
        </div>
        <!-- /.card -->
      </div>
      <!-- /.col (LEFT) -->
      <div class="col-md-6">
        <!-- LINE CHART -->
        <div class="card card-info">
          <div class="card-header">
            <h3 class="card-title">Line Chart</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div class="card-body">
            <div class="chart">
              <div class="chartjs-size-monitor">
                <div class="chartjs-size-monitor-expand">
                  <div class></div>
                </div>
                <div class="chartjs-size-monitor-shrink">
                  <div class></div>
                </div>
              </div>
              <canvas
                id="lineChart"
                style="height: 250px; min-height: 250px; display: block; width: 571px;"
                width="571"
                height="250"
                class="chartjs-render-monitor"
              ></canvas>
            </div>
          </div>
          <!-- /.card-body -->
        </div>
        <!-- /.card -->

        <!-- BAR CHART -->
        <div class="card card-success">
          <div class="card-header">
            <h3 class="card-title">Bar Chart</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div class="card-body">
            <div class="chart">
              <div class="chartjs-size-monitor">
                <div class="chartjs-size-monitor-expand">
                  <div class></div>
                </div>
                <div class="chartjs-size-monitor-shrink">
                  <div class></div>
                </div>
              </div>
              <canvas
                id="barChart"
                style="height: 230px; min-height: 230px; display: block; width: 571px;"
                width="571"
                height="230"
                class="chartjs-render-monitor"
              ></canvas>
            </div>
          </div>
          <!-- /.card-body -->
        </div>
        <!-- /.card -->

        <!-- STACKED BAR CHART -->
        <div class="card card-success">
          <div class="card-header">
            <h3 class="card-title">Stacked Bar Chart</h3>

            <div class="card-tools">
              <button type="button" class="btn btn-tool" data-widget="collapse">
                <i class="fas fa-minus"></i>
              </button>
              <button type="button" class="btn btn-tool" data-widget="remove">
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
          <div class="card-body">
            <div class="chart">
              <div class="chartjs-size-monitor">
                <div class="chartjs-size-monitor-expand">
                  <div class></div>
                </div>
                <div class="chartjs-size-monitor-shrink">
                  <div class></div>
                </div>
              </div>
              <canvas
                id="stackedBarChart"
                style="height: 230px; min-height: 230px; display: block; width: 571px;"
                width="571"
                height="230"
                class="chartjs-render-monitor"
              ></canvas>
            </div>
          </div>
          <!-- /.card-body -->
        </div>
        <!-- /.card -->
      </div>
      <!-- /.col (RIGHT) -->
    </div>
    <!-- /.row -->
  </div>
</template>

<script>
export default {
  mounted() {
    console.log("Component mounted.");
  }
};
</script>
