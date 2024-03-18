<template>
  <div class="dashboard p-4">
    <!-- end nav -->
    <div class="mt-2 w-full">
      <div
        class="lg:flex grid-cols-1 lg:space-y-0 space-y-3 gap-5 justify-between"
      >
        <div>
          <p class="uppercase text-xs text-gray-700 font-semibold">overview</p>
          <h1 class="text-2xl text-gray-900 dark:text-gray-200 font-medium">
            Dashboard Report HaloBPS
          </h1>
        </div>
        <div class="flex gap-2">
          <a href="http://localhost:8080/" target="_blank">
            <button
              class="bg-white dark:bg-gray-800 border flex gap-2 hover:border-gray-200 dark:hover:bg-gray-700 rounded py-3 px-5"
            >
              <span class="icon text-2xl"
                ><Icon icon="material-symbols:download"
              /></span>
              <span class="text"> Download Report</span>
            </button>
          </a>
          <button
            class="bg-white dark:bg-gray-800 hover:border-gray-200 dark:hover:bg-gray-700 dark:text-white dark:border-gray-700 border rounded py-2 px-5"
          >
            <a href="http://localhost:4000/" target="_blank">
              New Data Model
            </a>
          </button>
          <a href="http://localhost:8080/" target="_blank">
            <button
              class="bg-primary border flex gap-2 text-white hover:bg-primary/80 dark:border-gray-700 rounded py-3 px-5"
            >
              <span class="icon text-2xl"><Icon icon="ic:twotone-plus" /></span>
              <span class="text"> Create New Report</span>
            </button>
          </a>
        </div>
      </div>
    </div>

    <!-- grid wrapper card -->
    <div
      class="wrapper-card grid lg:grid-cols-4 grid-cols-1 md:grid-cols-2 gap-2 mt-5"
    >
      <!-- card  -->
      <div
        class="card bg-white dark:bg-gray-800 w-full rounded-md p-5 border dark:border-gray-700 flex"
      >
        <div class="p-2 max-w-sm">
          <div
            class="bg-orange-200 rounded-full w-14 h-14 text-lg p-3 text-orange-600 mx-auto"
          >
            <span class="">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="30px"
                height="30px"
                viewBox="0 0 24 24"
              >
                <path
                  fill="currentColor"
                  d="m13.817 5.669l4.504 4.501l-8.15 8.15l-4.501-4.504zm-3.006 13.944l8.8-8.8a.894.894 0 0 0 .001-1.28l-5.156-5.156a.926.926 0 0 0-1.28.001l-8.8 8.8a.894.894 0 0 0-.001 1.28l5.156 5.156a.926.926 0 0 0 1.28-.001m12.663-9.073L10.556 23.473c-.332.326-.787.527-1.289.527s-.957-.201-1.289-.527L6.184 21.68a2.74 2.74 0 0 0-3.875-3.874l.001-.001l-1.781-1.794c-.326-.332-.527-.787-.527-1.289s.201-.957.527-1.289L13.448.527C13.78.201 14.235 0 14.737 0s.957.201 1.289.527l1.781 1.781a2.74 2.74 0 1 0 3.874 3.874l.001-.001l1.794 1.781c.326.332.527.787.527 1.289s-.201.957-.527 1.289z"
                />
              </svg>
            </span>
          </div>
        </div>

        <div class="block p-2 w-full">
          <p class="font-semibold text-gray-900 dark:text-gray-200 text-xl">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicket"
              chartType="number"
            />
          </p>
          <h2 class="font-normal text-gray-400 text-md mt-1">Total Tiket</h2>
        </div>
      </div>
      <!-- end card -->
      <div
        class="card bg-white dark:bg-gray-800 w-full rounded-md p-5 border dark:border-gray-700 flex"
      >
        <div class="p-2 max-w-sm">
          <div
            class="bg-green-200 rounded-full w-14 h-14 text-lg p-3 text-green-600 mx-auto"
          >
            <span class="">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="30px"
                height="30px"
                viewBox="0 0 576 512"
              >
                <path
                  fill="currentColor"
                  d="M128 160h320v192H128zm400 96c0 26.51 21.49 48 48 48v96c0 26.51-21.49 48-48 48H48c-26.51 0-48-21.49-48-48v-96c26.51 0 48-21.49 48-48s-21.49-48-48-48v-96c0-26.51 21.49-48 48-48h480c26.51 0 48 21.49 48 48v96c-26.51 0-48 21.49-48 48m-48-104c0-13.255-10.745-24-24-24H120c-13.255 0-24 10.745-24 24v208c0 13.255 10.745 24 24 24h336c13.255 0 24-10.745 24-24z"
                />
              </svg>
            </span>
          </div>
        </div>

        <div class="block p-2 w-full">
          <p class="font-semibold text-gray-900 dark:text-gray-200 text-xl">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketAssign"
              chartType="number"
            />
          </p>
          <h2 class="font-normal text-gray-400 text-md mt-1">Ticket Assign</h2>
        </div>
      </div>
      <!-- end card -->
      <div
        class="card bg-white dark:bg-gray-800 w-full rounded-md p-5 border dark:border-gray-700 flex"
      >
        <div class="p-2 max-w-sm">
          <div
            class="bg-red-200 rounded-full w-14 h-14 text-lg p-3 text-red-600 mx-auto"
          >
            <span class="">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                aria-hidden="true"
                role="img"
                width="30px"
                height="30px"
                preserveAspectRatio="xMidYMid meet"
                viewBox="0 0 32 32"
              >
                <path
                  fill="none"
                  d="M8.007 24.93A4.996 4.996 0 0 1 13 20h6a4.996 4.996 0 0 1 4.993 4.93a11.94 11.94 0 0 1-15.986 0ZM20.5 12.5A4.5 4.5 0 1 1 16 8a4.5 4.5 0 0 1 4.5 4.5Z"
                />
                <path
                  fill="currentColor"
                  d="M26.749 24.93A13.99 13.99 0 1 0 2 16a13.899 13.899 0 0 0 3.251 8.93l-.02.017c.07.084.15.156.222.239c.09.103.187.2.28.3c.28.304.568.596.87.87c.092.084.187.162.28.242c.32.276.649.538.99.782c.044.03.084.069.128.1v-.012a13.901 13.901 0 0 0 16 0v.012c.044-.031.083-.07.128-.1c.34-.245.67-.506.99-.782c.093-.08.188-.159.28-.242c.302-.275.59-.566.87-.87c.093-.1.189-.197.28-.3c.071-.083.152-.155.222-.24ZM16 8a4.5 4.5 0 1 1-4.5 4.5A4.5 4.5 0 0 1 16 8ZM8.007 24.93A4.996 4.996 0 0 1 13 20h6a4.996 4.996 0 0 1 4.993 4.93a11.94 11.94 0 0 1-15.986 0Z"
                />
              </svg>
            </span>
          </div>
        </div>

        <div class="block p-2 w-full">
          <p class="font-semibold text-gray-900 dark:text-gray-200 text-xl">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalUserQuery"
              chartType="number"
            />
          </p>
          <h2 class="font-normal text-gray-400 text-md mt-1">Total Users</h2>
        </div>
      </div>
      <!-- end card -->
      <div
        class="card bg-white dark:bg-gray-800 w-full rounded-md p-5 border dark:border-gray-700 flex"
      >
        <div class="p-2 max-w-sm">
          <div
            class="bg-purple-200 rounded-full w-14 h-14 text-lg p-3 text-purple-600 mx-auto"
          >
            <span class="">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                aria-hidden="true"
                role="img"
                width="30px"
                height="30px"
                preserveAspectRatio="xMidYMid meet"
                viewBox="0 0 16 16"
              >
                <g fill="currentColor">
                  <path d="M15 13v1H1.5l-.5-.5V0h1v13h13Z" />
                  <path
                    d="M13 3.207L7.854 8.354h-.708L5.5 6.707l-3.646 3.647l-.708-.708l4-4h.708L7.5 7.293l5.146-5.147h.707l2 2l-.707.708L13 3.207Z"
                  />
                </g>
              </svg>
            </span>
          </div>
        </div>

        <div class="block p-2 w-full">
          <p class="font-semibold text-gray-900 dark:text-gray-200 text-xl">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalLoginQuery"
              chartType="number"
            />
          </p>
          <h2 class="font-normal text-gray-400 text-md mt-1">Total Visit</h2>
        </div>
      </div>
      <!-- end card -->
    </div>
    <!-- end wrapper card -->

    <div class="mt-2 lg:flex block lg:gap-2">
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketLayananBPS"
              chartType="number"
            />
          </h2>
          Kategori Layanan BPS
          <p class="text-gray-400 font-lexend font-normal">
            Ticket by entities
          </p>
          <span class="float-right">
            <!-- <h2 class="text-green-500 -mt-12 flex">
              <span class="mr-2"> 27.9% </span
              ><span>
                <Icon icon="akar-icons:arrow-up" />
              </span>
            </h2> -->
          </span>
        </div>
        <div class="wrapper-chart mt-5 pr-2 pl-2">
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="BarchartEntites"
            chartType="bar"
            style="height: 400px"
          />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 days</option>
              </select>
              <button class="uppercase border-b border-red-600 text-red-600">
                Entities Report
              </button>
            </div>
          </div>
        </div>
      </div>
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketGangguan"
              chartType="number"
            />
          </h2>
          Kategori Tipe Gangguan
          <p class="text-gray-400 font-lexend font-normal">Ticket by type</p>
        </div>
        <div class="wrapper-chart mt-5">
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="TypeTicketQuery"
            chartType="pie"
            style="height: 350px"
          />
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 days</option>
              </select>
              <button class="uppercase border-b border-red-600 text-red-600">
                Vistor Report
              </button>
            </div>
          </div>
        </div>
      </div>
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketUrgencySedang"
              chartType="number"
            />
          </h2>
          Kategori Tipe Sedang
          <p class="text-gray-400 font-lexend font-normal">Ticket by urgency</p>
        </div>

        <div class="wrapper-chart mt-5">
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="BarchartUrgency"
            chartType="bar"
            style="height: 400px"
          />

          <div class="p-3"></div>
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 border dark:border-gray-700 max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 years</option>
              </select>

              <button class="uppercase border-b border-red-600 text-red-600">
                User Report
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="mt-2 lg:flex block lg:gap-2">
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketStatusNew"
              chartType="number"
            />
          </h2>
          Kategori Status New
          <p class="text-gray-400 font-lexend font-normal">Ticket by status</p>
          <span class="float-right">
            <!-- <h2 class="text-green-500 -mt-12 flex">
              <span class="mr-2"> 27.9% </span
              ><span>
                <Icon icon="akar-icons:arrow-up" />
              </span>
            </h2> -->
          </span>
        </div>
        <div class="wrapper-chart mt-5 pr-2 pl-2">
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="BarchartStatus"
            chartType="pie"
            style="height: 400px"
          />

          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 days</option>
              </select>
              <button class="uppercase border-b border-red-600 text-red-600">
                Entities Report
              </button>
            </div>
          </div>
        </div>
      </div>
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            <!-- <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketStatusNew"
              chartType="number"
            /> -->
          </h2>
          Kategori Tiket berdasarkan jenis BMN
          <p class="text-gray-400 font-lexend font-normal">Ticket by BMN</p>
          <span class="float-right">
            <!-- <h2 class="text-green-500 -mt-12 flex">
              <span class="mr-2"> 27.9% </span
              ><span>
                <Icon icon="akar-icons:arrow-up" />
              </span>
            </h2> -->
          </span>
        </div>
        <div class="wrapper-chart mt-5">
          <!-- <apexchart
            width="100%"
            height="380"
            type="area"
            :options="optionsVisitor"
            :series="seriesVisitor"
          ></apexchart> -->
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="BarchartAsset"
            chartType="bar"
            style="height: 400px"
          />
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 days</option>
              </select>
              <button class="uppercase border-b border-red-600 text-red-600">
                Vistor Report
              </button>
            </div>
          </div>
        </div>
      </div>
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            <ChartRenderer
              :cubejs-api="cubejsApi"
              :query="TotalTicketGroupSIS"
              chartType="number"
            />
          </h2>
          Kategori Group Operator Dir. SIS
          <p class="text-gray-400 font-lexend font-normal">Ticket by type</p>
        </div>

        <div class="wrapper-chart mt-5">
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="PiechartTicketGroups"
            chartType="pie"
            style="height: 350px"
          />

          <div class="p-3"></div>
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 border dark:border-gray-700 max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 years</option>
              </select>

              <button class="uppercase border-b border-red-600 text-red-600">
                User Report
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="mt-2 lg:flex block lg:gap-2 relative">
      <div
        class="bg-white dark:bg-gray-800 p-0 lg:w-3/4 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="p-5 flex justify-between">
          <div>
            <h2 class="font-medium text-sm text-gray-800 dark:text-gray-200">
              Ticket Assign
            </h2>
            <h1 class="font-semibold text-4xl text-gray-800 dark:text-gray-200">
              72%
            </h1>

            <p class="text-gray-400 font-lexend font-normal">
              Ticket assign chart per-month
            </p>
          </div>

          <div class="flex gap-5">
            <span class="">
              <h2 class="text-red-500 flex">
                <span class="mr-2"> 15.9% </span
                ><span>
                  <Icon icon="akar-icons:arrow-down" />
                </span>
              </h2>
            </span>
            <span class="">
              <h2 class="text-green-500 flex">
                <span class="mr-2"> 87.9% </span
                ><span>
                  <Icon icon="akar-icons:arrow-up" />
                </span>
              </h2>
            </span>
          </div>
        </div>

        <ChartRenderer
          :cubejs-api="cubejsApi"
          :query="TicketByMonthQuery"
          chartType="line"
        />
        <br />
        <hr />
        <div class="wrapper-button p-5 flex justify-between mt-3">
          <select
            name=""
            id=""
            class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
          >
            <option value="">Last 7 years</option>
          </select>
          <button class="uppercase border-b border-red-600 text-red-600">
            Sales Report
          </button>
        </div>
      </div>
      <div
        class="bg-white dark:bg-gray-800 p-5 lg:mt-0 mt-4 lg:w-2/4 border dark:border-gray-700 rounded-md w-full"
      >
        <div class="">
          <h2 class="text-lg font-semibold dark:text-gray-200">
            PARTNER SALES
          </h2>
          <p class="text-gray-400">This is list if your partner online.</p>
        </div>
        <perfect-scrollbar class="divide-y h-96 mt-5 dark:divide-gray-700">
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user1.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Elizabeth Begum</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  Active now
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user2.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Ethan Roger</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  Active now
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user3.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Tobi Ferreira</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  last online 2 hours ago
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user4.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Taylor neal</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  last online 2 minutes ago
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user5.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Bruno Barron</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  last online 2 hours ago
                </p>
              </div>
            </div>
          </div>
        </perfect-scrollbar>
      </div>
    </div>

    <!-- <div class="mt-2 lg:flex block lg:gap-2 relative">
      <div
        class="bg-white dark:bg-gray-800 p-0 lg:w-3/4 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="p-5 flex justify-between">
          <div>
            <h2 class="font-medium text-sm text-gray-800 dark:text-gray-200">
              SALES
            </h2>
            <h1 class="font-semibold text-4xl text-gray-800 dark:text-gray-200">
              72%
            </h1>

            <p class="text-gray-400 font-lexend font-normal">
              your sales chart per-years
            </p>
          </div>

          <div class="flex gap-5">
            <span class="">
              <h2 class="text-red-500 flex">
                <span class="mr-2"> 15.9% </span
                ><span>
                  <Icon icon="akar-icons:arrow-down" />
                </span>
              </h2>
            </span>
            <span class="">
              <h2 class="text-green-500 flex">
                <span class="mr-2"> 87.9% </span
                ><span>
                  <Icon icon="akar-icons:arrow-up" />
                </span>
              </h2>
            </span>
          </div>
        </div>

        <apexchart
          width="100%"
          height="260"
          type="area"
          :options="optionsArea"
          :series="seriesArea"
          :sparkline="{
            enabled: true,
          }"
        ></apexchart>
        <br />
        <hr />
        <div class="wrapper-button p-5 flex justify-between mt-3">
          <select
            name=""
            id=""
            class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
          >
            <option value="">Last 7 years</option>
          </select>
          <button class="uppercase border-b border-red-600 text-red-600">
            Sales Report
          </button>
        </div>
      </div>
      <div
        class="bg-white dark:bg-gray-800 p-5 lg:mt-0 mt-4 lg:w-2/4 border dark:border-gray-700 rounded-md w-full"
      >
        <div class="">
          <h2 class="text-lg font-semibold dark:text-gray-200">
            PARTNER SALES
          </h2>
          <p class="text-gray-400">This is list if your partner online.</p>
        </div>
        <perfect-scrollbar class="divide-y h-96 mt-5 dark:divide-gray-700">
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user1.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Elizabeth Begum</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  Active now
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user2.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Ethan Roger</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  Active now
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user3.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Tobi Ferreira</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  last online 2 hours ago
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user4.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Taylor neal</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  last online 2 minutes ago
                </p>
              </div>
            </div>
          </div>
          <div class="p-3 w-full">
            <div class="flex gap-5">
              <div>
                <img
                  class="w-14 rounded-md"
                  src="../assets/img/user5.png"
                  alt=""
                />
              </div>
              <div class="mt-1">
                <h2 class="dark:text-gray-200">Bruno Barron</h2>
                <p class="text-sm dark:text-gray-500 text-gray-400">
                  last online 2 hours ago
                </p>
              </div>
            </div>
          </div>
        </perfect-scrollbar>
      </div>
    </div>

    <div class="mt-2 lg:flex block lg:gap-2">
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            1,780
          </h2>
          <p class="text-gray-400 font-lexend font-normal">
            New products this week
          </p>
          <span class="float-right">
            <h2 class="text-green-500 -mt-12 flex">
              <span class="mr-2"> 27.9% </span
              ><span>
                <Icon icon="akar-icons:arrow-up" />
              </span>
            </h2>
          </span>
        </div>
        <div class="wrapper-chart mt-5 pr-2 pl-2">
          <apexchart
            width="100%"
            height="380"
            type="bar"
            :options="optionsBar"
            :series="seriesBar"
          ></apexchart>
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 days</option>
              </select>
              <button class="uppercase border-b border-red-600 text-red-600">
                Product Report
              </button>
            </div>
          </div>
        </div>
      </div>
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            5,355
          </h2>
          <p class="text-gray-400 font-lexend font-normal">Visitor this week</p>

          <span class="float-right">
            <h2 class="text-green-500 -mt-12 flex">
              <span class="mr-2"> 47.9% </span
              ><span>
                <Icon icon="akar-icons:arrow-up" />
              </span>
            </h2>
          </span>
        </div>
        <div class="wrapper-chart mt-5">
          <apexchart
            width="100%"
            height="380"
            type="area"
            :options="optionsVisitor"
            :series="seriesVisitor"
          ></apexchart>
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 dark:border-gray-700 border max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 days</option>
              </select>
              <button class="uppercase border-b border-red-600 text-red-600">
                Vistor Report
              </button>
            </div>
          </div>
        </div>
      </div>
      <div
        class="mt-2 bg-white dark:bg-gray-800 p-0 w-full rounded-md box-border border dark:border-gray-700"
      >
        <div class="head p-5">
          <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
            475
          </h2>
          <p class="text-gray-400 font-lexend font-normal">
            User signups this week
          </p>
        </div>

        <div class="wrapper-chart mt-5">
          <apexchart
            width="100%"
            height="380"
            type="pie"
            :options="optionsDonut"
            :series="seriesDonut"
          ></apexchart>
          <div class="p-3"></div>
          <br />
          <hr />
          <div class="footer p-5">
            <div class="wrapper-button flex justify-between mt-3">
              <select
                name=""
                id=""
                class="dark:bg-gray-800 dark:hover:bg-gray-700 border dark:border-gray-700 max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
              >
                <option value="">Last 7 years</option>
              </select>

              <button class="uppercase border-b border-red-600 text-red-600">
                User Report
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div
      class="mt-2 bg-white dark:bg-gray-800 p-5 w-full rounded-md box-border border dark:border-gray-700"
    >
      <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
        Latest Transactions
      </h2>
      <p class="text-gray-400 font-lexend font-normal">
        This is a list of latest transactions
      </p>
      <div class="wrapping-table mt-10">
        <table
          class="w-full text-sm text-left text-gray-500 dark:text-gray-400 lg:overflow-auto overflow-x-scroll"
        >
          <thead
            class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400"
          >
            <tr>
              <th scope="col" class="uppercase px-6 py-3">Transaction</th>
              <th scope="col" class="uppercase px-6 py-3">Date & Time</th>
              <th scope="col" class="uppercase px-6 py-3">Amount</th>
              <th scope="col" class="uppercase px-6 py-3">Status</th>
            </tr>
          </thead>
          <tbody>
            <tr
              class="bg-white border-b dark:bg-gray-800 dark:border-gray-700 odd:bg-white even:bg-gray-50"
              v-for="items in tableTransaction"
              :key="items.transaction"
            >
              <td class="px-6 py-4">
                {{ items.transaction }}
              </td>
              <td class="px-6 py-4">
                {{ items.datetime }}
              </td>
              <td class="px-6 py-4">
                {{ items.amount }}
              </td>
              <td class="px-6 py-4">
                <span
                  class="text-green-800 bg-green-300 px-3 py-1 rounded-md"
                  v-if="items.statusTransaction == 'completed'"
                >
                  {{ items.statusTransaction }}
                </span>
                <span
                  class="text-purple-800 bg-purple-300 px-3 py-1 rounded-md"
                  v-else-if="items.statusTransaction == 'progress'"
                >
                  {{ items.statusTransaction }}
                </span>
                <span
                  class="text-red-800 bg-red-300 px-3 py-1 rounded-md"
                  v-else
                >
                  {{ items.statusTransaction }}
                </span>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
      <div class="wrapper-button flex justify-between mt-3">
        <select
          name=""
          id=""
          class="dark:bg-gray-800 dark:hover:bg-gray-700 border dark:border-gray-700 max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
        >
          <option value="">Last 7 years</option>
        </select>
        <button class="uppercase border-b border-red-600 text-red-600">
          Transaction Report
        </button>
      </div>
    </div>
    <div
      class="mt-2 bg-white dark:bg-gray-800 p-5 w-full rounded-md box-border border dark:border-gray-700"
    >
      <h2 class="font-bold text-lg text-gray-800 dark:text-gray-200">
        Latest Ticket Assign
      </h2>
      <p class="text-gray-400 font-lexend font-normal">
        This is a list of latest assign
      </p>
      <div class="wrapping-table mt-10">
        <table
          class="w-full text-sm text-left text-gray-500 dark:text-gray-400 lg:overflow-auto overflow-x-scroll"
        >
          <ChartRenderer
            :cubejs-api="cubejsApi"
            :query="TableLatestAssign"
            chartType="table"
          />
        </table>
      </div>
      <div class="wrapper-button flex justify-between mt-3">
        <select
          name=""
          id=""
          class="dark:bg-gray-800 dark:hover:bg-gray-700 border dark:border-gray-700 max-w-lg px-4 py-3 block rounded-md text-gray-500 dark:text-gray-400"
        >
          <option value="">Last 7 years</option>
        </select>
        <button class="uppercase border-b border-red-600 text-red-600">
          Transaction Report
        </button>
      </div>
    </div> -->
  </div>
</template>

<script>
// @ is an alias to /src
import { Icon } from "@iconify/vue";
import cubejs from "@cubejs-client/core";
import { QueryRenderer } from "@cubejs-client/vue3";
import ChartRenderer from "./components/ChartRenderer.vue";

const cubejsApi = cubejs(
  "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpYXQiOjE3MDc1NTg2MjksImV4cCI6MTcwNzY0NTAyOX0.VZIbz44QKj7RJ-h5-V-9Y4nZzk7prV1msKJ5kiPgHUs",
  {
    apiUrl: "http://localhost:4000/cubejs-api/v1",
  }
);
export default {
  name: "Dashboard",
  components: {
    Icon,
    ChartRenderer,
  },
  data() {
    return {
      cubejsApi,
      query: {
        measures: ["jumlah_tiket_berdasarkan_kategori_layanan_alltime.count"],
        order: {
          "jumlah_tiket_berdasarkan_kategori_layanan_alltime.count": "desc",
        },
        dimensions: [
          "jumlah_tiket_berdasarkan_kategori_layanan_alltime.unitkerja",
        ],
      },
      query2: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_tickets.urgency"],
        order: {
          "glpi_tickets.count": "desc",
        },
      },
      TotalTicket: {
        measures: ["glpi_tickets.count"],
      },
      TotalUserQuery: {
        measures: ["glpi_users.count"],
      },
      TotalLoginQuery: {
        measures: ["glpi_events.TotalLogin"],
        dimensions: ["glpi_events.service"],
        order: {
          "glpi_events.TotalLogin": "desc",
        },
        timeDimensions: [],
      },
      TotalTicketAssign: {
        measures: ["glpi_tickets.TotalTiketAssign"],
        dimensions: ["glpi_tickets.status"],
        timeDimensions: [],
        order: {
          "glpi_tickets.TotalTiketAssign": "desc",
        },
      },
      TotalTicketLayananBPS: {
        measures: ["glpi_tickets.TotalTicketLayananBPS"],
        dimensions: ["glpi_tickets.entities_id"],
      },
      TotalTicketGangguan: {
        measures: ["glpi_tickets.TotalTicketGangguan"],
        dimensions: ["glpi_tickets.type"],
      },
      TotalTicketStatusNew: {
        measures: ["glpi_tickets.TotalTicketStatusNew"],
        dimensions: ["glpi_tickets.status"],
      },
      TotalTicketGroupSIS: {
        measures: ["glpi_groups_tickets.TotalTicketGroupSIS"],
        dimensions: ["glpi_groups_tickets.groups_id"],
      },
      TotalTicketUrgencySedang: {
        measures: ["glpi_tickets.TotalTicketUrgencySedang"],
        dimensions: ["glpi_tickets.urgency"],
      },
      TableLatestAssign: {
        dimensions: [
          "glpi_tickets.name",
          "glpi_tickets.status",
          "glpi_tickets.urgency",
          "glpi_tickets.type",
          "glpi_tickets.date",
        ],
        order: [["glpi_tickets.id", "desc"]],
        limit: 10,
      },
      BarchartEntites: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_entities.name"],
        order: {
          "glpi_entities.name": "desc",
        },
      },
      BarchartUrgency: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_tickets.urgency"],
        order: {
          "glpi_tickets.urgency": "asc",
        },
      },
      BarchartStatus: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_tickets.status"],
        order: {
          "glpi_tickets.status": "asc",
        },
      },
      TypeTicketQuery: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_tickets.type"],
      },
      PiechartTicketGroups: {
        measures: ["glpi_groups_tickets.count"],
        dimensions: ["glpi_groups.name"],
      },
      TicketByMonthQuery: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_tickets.date"],
        order: [["glpi_tickets.date", "asc"]],
      },
      BarchartAsset: {
        measures: ["glpi_tickets.count"],
        dimensions: ["glpi_assets.name"],
        order: {
          "glpi_tickets.date": "asc",
        },
        filters: [
          {
            member: "glpi_assets.name",
            operator: "notEquals",
            values: ["non-bmn"],
          },
        ],
      },
      // for more guide apexchart.js
      // https://apexcharts.com/docs/chart-types/line-chart/

      // chart data area
      optionsArea: {
        xaxis: {
          categories: [2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022],
        },
        fontFamily: "Segoe UI, sans-serif",
        stroke: {
          curve: "straight",
        },
        chart: {
          toolbar: {
            show: true,
          },
          zoom: {
            enabled: false,
          },
          sparkline: {
            enabled: true,
          },
        },
        markers: {
          size: 0,
        },
        yaxis: {
          show: false,
        },
        fill: {
          type: "gradient",
          gradient: {
            shadeIntensity: 0,
            opacityFrom: 0.2,
            opacityTo: 0.5,
            stops: [0, 90, 100],
          },
        },
      },

      chart: {
        fontFamily: "lexend, sans-serif",
      },

      seriesArea: [
        {
          name: "Revenue",
          data: [30, 40, 45, 50, 49, 60, 70, 91],
        },
        {
          name: "Revenue (Previous period)",
          data: [20, 34, 45, 55, 79, 87, 90, 98],
        },
      ],
      optionsBar: {
        chart: {
          toolbar: {
            show: false,
          },
          zoom: {
            enabled: false,
          },
          sparkline: {
            enabled: true,
          },
        },
        legend: {
          show: false,
        },
        xaxis: {
          show: false,
        },
        yaxis: {
          show: false,
        },
        colors: ["#4f46e5", "#DC2626"],
        dataLabels: {
          enabled: false,
        },
        stroke: {
          curve: "straight",
        },
      },

      seriesBar: [
        {
          name: "Product 1",
          data: [30, 40, 45, 50, 49, 60, 70, 91],
        },
        {
          name: "Product 2",
          data: [20, 34, 45, 55, 79, 87, 90, 98],
        },
      ],
      optionsVisitor: {
        chart: {
          toolbar: {
            show: false,
          },
          zoom: {
            enabled: false,
          },
          sparkline: {
            enabled: true,
          },
        },
        legend: {
          show: false,
        },
        xaxis: {
          show: false,
        },
        yaxis: {
          show: false,
        },
        colors: ["#4f46e5"],
        dataLabels: {
          enabled: false,
        },
        fill: {
          type: "gradient",
          gradient: {
            shadeIntensity: 0,
            opacityFrom: 0,
            opacityTo: 0.3,
            stops: [0, 90, 100],
          },
        },
        stroke: {
          curve: "smooth",
        },
      },

      seriesVisitor: [
        {
          name: "Visitor ",
          data: [30, 40, 45, 50, 49, 60, 70, 91],
        },
      ],
      optionsDonut: {
        chart: {
          type: "donut",
        },
        legend: false,
        dataLabels: {
          enabled: false,
        },
        labels: ["admin", "SuperAdmin", "User", "Costumer"],
      },

      seriesDonut: [20, 15, 63, 83],
      tableTransaction: [
        {
          transaction: "Payment from Ethan Roger",
          datetime: "Apr 22, 2022",
          amount: "Rp.450.000",
          statusTransaction: "completed",
        },
        {
          transaction: "Payment from Taylor neal",
          datetime: "May 2, 2022",
          amount: "Rp.250.000",
          statusTransaction: "completed",
        },
        {
          transaction: "Payment from Tobi Ferreira",
          datetime: "May 5, 2022",
          amount: "Rp.150.000",
          statusTransaction: "progress",
        },
        {
          transaction: "Payment failed from #046577",
          datetime: "May 5, 2022",
          amount: "Rp.180.000",
          statusTransaction: "cancelled",
        },
      ],
    };
    // end chart data line
  },

  mounted() {},
};
</script>
